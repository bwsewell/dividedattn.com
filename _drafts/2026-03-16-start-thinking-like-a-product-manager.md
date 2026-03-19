---
layout: post
title: "Sleeper Agents and the Product Manager Mindset"
date: 2026-03-16
---

The idea of configuring an agent with a queue of tasks before bed and waking up to finished pull requests still feels new enough that I'm not sure most developers have absorbed what it actually means.  It's not a workflow improvement in the way that a faster machine or a better editor is.  Something more fundamental is shifting, and I think the people closest to it are only starting to notice.

The shorthand I keep coming back to is "sleeper agents."  Not in the espionage sense, but the literal one.  Processes you configure with intent, point at a backlog, and leave running while you're not paying attention.  They don't need you in the loop.  They don't need you watching the terminal, reading output, nudging a response, or re-prompting when something drifts.  You write the description, you define what done looks like, and the work is there by the time you're awake.

This is genuinely different from how Claude Code started, and from how most developers still use it.  The early pattern — and still the default one — is sitting in the terminal, describing a problem, reading the output, correcting it, prompting again.  A fast pair programmer.  That model works, but it's also the slowest way to get value from the tool, and I've had enough late nights in that loop to say clearly that the quality of what comes back almost never improves with more real-time correction.  It correlates with the quality of the initial description.  The tight feedback loop feels productive.  It mostly just feels that way.

What I think is changing, and will change quickly, is that the job stops being about participating in the agent's process and starts being about defining the work the agent will execute.  You're no longer at the keyboard in the same way.  You're upstream of it.  Grooming a backlog.  Writing acceptance criteria.  Describing exactly what done looks like for each task.  Flagging which changes need a human eye on the diff and which ones an agent can review on its own.  That sounds a lot more like product management than what most engineers do today.

The building gets delegated.  The vision doesn't.  Knowing what to build, for whom, and why is still entirely a human problem.  So is translating a vague business need into a set of discrete, unambiguous tasks that an agent can actually execute without going sideways.  That translation is the skill that matters, and it's one most engineers haven't had to develop because they've always been the ones doing the execution themselves.

The developers who see this shift coming will spend their time differently.  Their workdays will be about queuing up work.  Their mornings will be about reviewing what got built overnight.  They'll get better at writing specs, thinking in stories and acceptance criteria, and learning to define work rather than doing it by hand.  The ones who keep white-knuckling the CLI terminal in the same feedback loop they started with will wish they had started sooner.

Start thinking like a product manager.  The tools will catch up to the workflow faster than you expect.
