---
layout: post
title: "Sleeper Agents"
---

The agentic coding tools are getting good. Claude Code, Codex, and their competitors are legitimately impressive. But I'm noticing a trend that bothers me: the labs are increasingly pushing features designed to keep agents coding *while you're not even at your computer*.

![Anthropic marketing Claude Code as "a proactive assistant that works on your behalf" while you're away](/assets/images/claude-proactive-assistant.png)
*Marketing I received in my inbox recently from Anthropic.*

Scheduled tasks. Background workers. Swarms pulling cards off your backlog overnight. The pitch is seductive, especially if you're paying for a subscription with a token cap on a rolling window. "You're leaving tokens on the table," they tell you. "Let your agents code while you sleep."

I tried it. It lasted about a week.

## The Diminishing Returns Problem

Anyone who has used an orchestration workflow where you're not present for the work knows the pattern. The bigger the task, the broader the scope, the more rework you inherit. AI tools can make certain tasks *take longer*, not shorter, because developers have to circle back and fix hallucinations, lost context, or just plain bad judgment calls.

Now scale that up. Imagine waking up to a dozen PRs you didn't supervise, touching code you haven't read, implementing features in ways you wouldn't have chosen. Within a week you're drowning in slop that no agent (and certainly not you) can meaningfully review. You've lost the thread of your own codebase.

## Why the Labs Push This

The uncharitable read: it's an optimization problem for them. They need you to burn tokens. Subscriptions that cap usage over a 5-hour window create a natural incentive to fill every window, including the ones at 3 AM. The marketing writes itself.

These overnight workers are an effective mechanism for earning the labs money. Every new feature drop sends a wave of users rushing to try it.

But earning the labs money and building good software are two different goals.

## What I Actually Do Instead

I'm a solo founder working on a side project alongside a full-time job. I'm exactly the target audience for "let agents code while you sleep." And I decided against it.

Instead, I've set up a workflow that keeps me in the driver's seat. I maintain a Notion board with a simple kanban: Backlog, Ready for Development, In Review, Done. When I spin up a dev worker agent, it follows a defined sequence:

1. Check open merge requests for any comments I've left. Address them, push changes.
2. Pick the next card off Ready for Development.
3. Open a branch. Write tests first. Follow the patterns and paradigms I've documented.
4. Open a PR. Never more than ~10 files. If a feature needs multiple PRs, that's fine.

Then I review the pull requests myself. I'm not outsourcing that step. I've enumerated my development preferences explicitly because I don't want agents writing code I can't understand. That's counterproductive when I'm the one who has to maintain it, debug it, and ship it.

## The Speed Trap

There's a vision floating around where the future of software development is grooming backlogs for agent swarms. You define the work, they execute around the clock, you maximize cost-per-token efficiency. It sounds like the logical endpoint.

It's not going to work. Not because the tools aren't capable, but because the human bottleneck is the point, not the problem.

If you keep a human in the loop, you can only move as fast as the human. That feels like a limitation. But if you remove the human, you get software that nobody understands, nobody can debug quickly, and nobody truly owns. Your agents own the roadmap. You're just the person grooming their backlog.

For solo founders especially: if you delegate everything to agents, your startup will be obvious slop. You won't know how to fix bugs quickly. You won't know how to respond to user feedback. You won't own any of it.

## Move Slowly

I know "move slowly" sounds wrong when the entire industry is screaming about acceleration. But even the "slow" pace here, one human reviewing agent-written PRs against a well-groomed backlog, is still remarkably fast compared to building everything from scratch by hand.

The trick is resisting the urge to optimize for token throughput when what you should be optimizing for is comprehension. Stay in the loop. Own your roadmap. The agents are tools, not replacements. And "sleeper agents" are, for now, mostly a way to generate work you'll spend tomorrow undoing.
