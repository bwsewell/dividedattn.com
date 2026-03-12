---
layout: post
title: "Ship It in Your Sleep"
date: 2026-03-12
---

You have a startup idea.  You've had it for years.  It lives in a note on your phone, or a bookmark folder, or a Notion page you haven't opened since 2024.  You think about it in the shower.  You think about it on your commute.  You never work on it because by the time you're done with your actual job and your actual life, you have zero energy left to write code.

I've been there.  I have a graveyard of side projects that never made it past "create-react-app."  But I recently figured out a workflow that lets me make real progress on my ideas without sacrificing my evenings, my weekends, or my sleep.

The setup: Trello, Claude Code, and a cron job.

## The Idea

Here's the premise.  You spend 30 minutes during lunch or on a Sunday morning breaking your idea into Trello cards.  You write each card the way you'd write a ticket for a junior developer — clear enough that someone with no context could pick it up and execute.  Then you let Claude Code work through the backlog overnight while you sleep.

You wake up.  You review the pull requests.  You merge what's good, leave comments on what's not, and move on with your day.

That's it.  That's the whole workflow.

## Setting Up the Board

Your Trello board needs four columns:

1. **Backlog** — everything you want built, roughly prioritized
2. **Up Next** — the cards Claude Code should work on in the next session
3. **In Progress** — what's currently being worked on
4. **Review** — completed work waiting for you to look at

The cards themselves matter more than the board structure.  Write them like you're onboarding a contractor who's never seen your codebase.  Be specific:

**Bad card:**
> Add authentication

**Good card:**
> Add email/password authentication using NextAuth.js with a PostgreSQL adapter.  Create a login page at /login and a signup page at /signup.  Use the existing Tailwind components in src/components/ui.  Store sessions in the database, not JWTs.  Add a middleware that redirects unauthenticated users to /login for all routes under /dashboard.

The more context you put in the card, the better the output.  Claude Code is good, but it's not psychic.  If you leave ambiguity, it'll make assumptions, and those assumptions might not match yours.

## The Overnight Script

This is where it gets fun.  You write a script that:

1. Pulls the top card from "Up Next" via the Trello API
2. Moves it to "In Progress"
3. Creates a new git branch
4. Feeds the card title and description to Claude Code as a prompt
5. Lets Claude Code do its thing — write code, run tests, iterate
6. Commits the work and pushes the branch
7. Opens a pull request with the card description as the PR body
8. Moves the card to "Review" and links the PR
9. Grabs the next card and repeats

You run this as a cron job that kicks off at midnight (or whenever you go to bed) and let it chew through your backlog.

The Trello API is straightforward.  A few REST calls to read cards and move them between lists.  The Claude Code CLI can be invoked headlessly with `claude -p "your prompt here"` and pointed at a working directory.  Wire these together with a bash script or a small Node/Python wrapper and you're in business.

## A Realistic Script Skeleton

Here's the rough shape of what the runner looks like.  This isn't copy-paste production code — it's the bones you'd flesh out for your own setup:

```bash
#!/bin/bash

TRELLO_KEY="your-key"
TRELLO_TOKEN="your-token"
BOARD_ID="your-board"
UP_NEXT_LIST="list-id-for-up-next"
IN_PROGRESS_LIST="list-id-for-in-progress"
REVIEW_LIST="list-id-for-review"
PROJECT_DIR="$HOME/projects/your-startup"

get_next_card() {
  curl -s "https://api.trello.com/1/lists/$UP_NEXT_LIST/cards?key=$TRELLO_KEY&token=$TRELLO_TOKEN" \
    | jq -r '.[0]'
}

move_card() {
  curl -s -X PUT "https://api.trello.com/1/cards/$1/idList?key=$TRELLO_KEY&token=$TRELLO_TOKEN&value=$2"
}

while true; do
  CARD=$(get_next_card)
  CARD_ID=$(echo "$CARD" | jq -r '.id')
  CARD_NAME=$(echo "$CARD" | jq -r '.name')
  CARD_DESC=$(echo "$CARD" | jq -r '.desc')

  [ "$CARD_ID" = "null" ] && echo "No more cards." && break

  # Move to In Progress
  move_card "$CARD_ID" "$IN_PROGRESS_LIST"

  # Branch and build
  cd "$PROJECT_DIR"
  BRANCH="feature/$(echo "$CARD_NAME" | tr ' ' '-' | tr '[:upper:]' '[:lower:]')"
  git checkout main && git pull && git checkout -b "$BRANCH"

  # Let Claude Code work
  claude -p "You are working on this project. Here is your task:

  Title: $CARD_NAME

  Description: $CARD_DESC

  Work in the current directory. Write code, run tests if they exist,
  and make sure everything works before you're done." \
  --allowedTools "Edit,Write,Bash,Read,Glob,Grep" \
  --max-turns 50

  # Commit, push, open PR
  git add -A && git commit -m "$CARD_NAME"
  git push -u origin "$BRANCH"
  gh pr create --title "$CARD_NAME" --body "$CARD_DESC"

  # Move to Review
  move_card "$CARD_ID" "$REVIEW_LIST"
done
```

You'd obviously add error handling, logging, and probably link the PR URL back to the Trello card as a comment.  But the core loop is: pull card, branch, prompt, commit, PR, next.

## Agent Teams: Power and Pain

Claude Code supports agent teams — you can spawn multiple sub-agents that work in parallel on different parts of a task.  In theory, this means you could have one agent writing the frontend component while another writes the API endpoint while a third writes the tests.

In practice, be careful.  Each sub-agent burns through your token quota independently.  A single complex card might use 50-100k tokens on its own.  Spawn three agents for one card and you've tripled that.  If you're on a plan with a 5-hour usage window and a token cap, agent teams can blow through your entire quota on two or three cards.

My advice: use agent teams for cards that are genuinely parallelizable — like "build these three independent API endpoints" — and stick to single-agent execution for everything else.  The throughput gain from parallelism rarely justifies the quota cost unless the tasks are truly independent.

## Working Around Quota Limits

Here's the part nobody talks about.  Claude Code has usage limits that reset on a rolling 5-hour window.  If your overnight runner is aggressive, it'll hit the ceiling after a few cards and stall.

You have two options:

**Option 1: Pace yourself.**  Add a delay between cards.  If you know your quota allows roughly N tokens per 5-hour window, estimate how many tokens each card will consume (check your usage dashboard after a few runs) and space the cards accordingly.  You might only get 3-4 cards per window, but they'll all complete cleanly.

**Option 2: Burn and wait.**  Run cards as fast as possible until you hit the limit.  When Claude Code returns a rate limit error, parse the reset time from the response, sleep until the next window opens, and resume.  This maximizes throughput over an 8-hour sleep window — you'll get one full burst, hit the wall, wait, then get a second burst.

I use option 2.  The script looks roughly like this:

```bash
run_card() {
  # ... the card processing logic from above ...
}

while true; do
  CARD=$(get_next_card)
  [ "$(echo "$CARD" | jq -r '.id')" = "null" ] && break

  OUTPUT=$(run_card "$CARD" 2>&1)

  if echo "$OUTPUT" | grep -q "rate limit\|quota\|429"; then
    echo "Quota hit at $(date). Sleeping until next window..."
    sleep 18000  # 5 hours
    echo "Resuming at $(date)."
    continue
  fi
done
```

Over an 8-hour night, this typically gets me two full windows of work.  That's 6-8 cards, which is a genuinely meaningful amount of progress on a side project.

## What You Wake Up To

Here's what a good morning looks like with this setup:

- 3-6 pull requests sitting in GitHub, each tied to a Trello card
- Your "Review" column has cards with PR links
- Your "Up Next" column is lighter than when you went to bed
- You spend 20-30 minutes reviewing diffs over coffee
- You merge the good ones, leave comments on the ones that need adjustment, and move the comment cards back to "Up Next" with notes

It's like having a junior developer who works the night shift.  The code isn't always perfect — sometimes Claude Code makes weird architectural choices, sometimes it misunderstands the card, sometimes the tests don't pass.  But even a 50% merge rate means you're shipping 2-3 features a night without writing a line of code yourself.

## The Cards That Work Best

After a few weeks of running this, I've learned which cards produce the best overnight results:

- **CRUD endpoints and database models.**  These are bread and butter.  Well-defined inputs and outputs, clear structure, easy to verify.
- **UI components with clear specs.**  "Build a settings page with these fields" works great.  "Make it look good" does not.
- **Integrations with documented APIs.**  "Connect to the Stripe API and create a checkout flow" with a link to the relevant docs usually comes back clean.
- **Test suites.**  "Write tests for all endpoints in src/api/" is a perfect overnight card.

And the cards that don't work well:

- **Vague architecture decisions.**  "Set up the project structure" without strong opinions in the description leads to choices you'll want to redo.
- **Anything requiring visual design judgment.**  Claude Code can write CSS but it can't taste.
- **Cards that depend on other cards.**  If card B needs card A's code to exist first, don't put them both in "Up Next" at the same time unless you've ordered them correctly.

## The Real Point

This isn't about replacing yourself.  It's about using the hours you're not available to make progress on the thing you care about but can't find time for.

You're a busy developer.  You have a job, maybe kids, definitely a life.  The idea has been sitting there for years because the math never worked — you can't code for 8 hours at work and then come home and code for 4 more hours on your thing.  That's how you burn out.

But you *can* spend 30 minutes writing good Trello cards.  And you can let something else execute on them while you're unconscious.

The startup idea doesn't need your nights and weekends.  It needs a backlog and a runner.

Set it up.  Go to sleep.  Wake up to pull requests.
