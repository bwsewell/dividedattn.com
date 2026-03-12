---
layout: post
title: "When the Interface Is the Institution"
date: 2026-03-12
---

I got to tour a Phoenix air traffic control tower recently.  I walked in the way most software engineers walk into unfamiliar environments — already designing the replacement in my head.  Legacy systems, green-on-black terminals, paper everything.  Surely this was a domain waiting to be reimagined by someone with a Figma account and good intentions.

<figure class="figure-margin">
  <img src="/assets/images/atc-tower-cab.jpg" alt="Interior of an airport traffic control tower cab">
  <figcaption>Inside a typical tower cab. Every surface serves a purpose. — FAA</figcaption>
</figure>

I was wrong.  Not because the technology was impressive in the way I'm used to technology being impressive.  But because it was *right*.  Every element in that cab existed for a reason that had been pressure-tested by decades of life-or-death operations.  The STARS radar scopes — green data blocks on dark backgrounds, zero design flourish — weren't under-designed.  They were finished.

And then there were the flight progress strips.

## Strips of Paper Running the Airspace

<figure class="figure-margin">
  <img src="/assets/images/stars-radar.jpg" alt="Controller using a STARS radar scope at El Paso TRACON">
  <figcaption>A controller at the STARS scope. Green data blocks, dark background, zero flourish. — FAA</figcaption>
</figure>

Flight progress strips are small slips of paper, printed with flight data, arranged on a board in front of each controller.  Their position on the board encodes meaning — which sector owns the aircraft, what phase of flight it's in, what's been coordinated and what hasn't.  Controllers physically move them, annotate them with pen marks, angle them.  The board is a real-time model of the airspace, maintained by hand.

The word "handoff" — which we use casually in software — literally comes from physically handing a strip to the next controller.  That's not a metaphor.  That's the origin.

<figure class="figure-inline">
  <img src="/assets/images/strip-bay-jakarta.jpg" alt="Flight progress strips arranged in a strip bay at Jakarta air traffic control">
  <figcaption>Paper strips in a strip bay at Jakarta Control.  Each strip's position on the board encodes status — sector ownership, phase of flight, coordination state.  The board is the interface. — Fred775 / Wikimedia Commons</figcaption>
</figure>

The FAA is rolling out electronic flight strips.  The digital replacement.  And it raises a question I've been thinking about ever since: what happens when the physical act of using a system is part of how the system works?

## The Low-Stakes Version

You've experienced a version of this yourself.  Think about the last time you went fully digital with your notes or your to-do list.  The app had everything — search, sync, reminders, tags.  Objectively better than a notebook in every measurable way.

And then you went back to pen and paper.  Because something about the physical act of writing helped you think.  Because crossing off a line item with a pen felt different than clicking a checkbox.  Because the notebook didn't have notifications.

When the stakes are low, we shrug at this.  Personal preference.  No big deal.

Now put that same human instinct in a room where the margin for error is measured in feet and seconds.  The stakes of a bad transition are not "I lost a to-do."  They're catastrophic.

## Digitization Is Not a UI Problem

The instinct in our industry is straightforward: map the manual process, build the digital equivalent, train the users, measure adoption.  If adoption is slow, that's a training problem.  Or a change management problem.  Or a user resistance problem.

This framing is wrong.

<figure class="figure-margin">
  <img src="/assets/images/flight-strips.png" alt="Paper flight progress strips used by air traffic controllers">
  <figcaption>Traditional paper strips before the digital transition. Each one is a live record maintained by hand. — FAA</figcaption>
</figure>

Paper strips don't just display data.  They create shared peripheral awareness — a controller can glance at another controller's board and see the state of their sector without asking.  They encode muscle memory — the physical act of moving a strip reinforces situational awareness in a way that clicking a button does not.  They're fault-tolerant in the most literal sense — paper doesn't crash, doesn't need a login, doesn't depend on a network.  When systems go down, the strips are still there.

None of this is in the spec.  None of it shows up in a feature comparison matrix.  But all of it is load-bearing.

Digitizing a system like this doesn't just change the medium.  It changes the social and cognitive contract the team built around that medium.  The parts of old systems that matter most are often invisible until you remove them and watch what breaks.

## The Hubris We're Trained Into

Software engineers are trained to find inefficiency and eliminate it.  That instinct is mostly good.  It's how we build things that are faster, cheaper, more scalable.

But it can cause us to mistake unfamiliarity for obsolescence.  We see paper and we pattern-match to "not yet digitized" instead of asking the harder question: why has this survived this long, under these stakes?

I'm not arguing that digital is wrong.  The electronic flight strip rollout has real benefits — better data integration, easier coordination across facilities, searchable history.  But trust is not a feature you ship in v1.  You don't earn the confidence of a profession that's been doing safety-critical work with paper for decades by showing them a slick interface and a training video.

Culture change is the product.  The software is just the delivery mechanism.

## What It Actually Reframed

<figure class="figure-inline">
  <img src="/assets/images/radar-scope.png" alt="Center radar scope display used by ARTCC controllers, showing aircraft positions and weather data">
  <figcaption>An ARTCC radar scope.  Slashes indicate light precipitation, Hs mark moderate rainfall.  This isn't a UI waiting for a redesign — it's a tool refined by decades of operational pressure. — FAA</figcaption>
</figure>

Standing in that tower cab changed how I see my own work.  In my career building web apps, the worst outcome of buggy software is an accidental email or a locked account.  Maybe a bad charge on a credit card.  Annoying, fixable, survivable.

Watching controllers work traffic — managing dozens of aircraft, making real-time decisions with real consequences — resets your frame of reference entirely.  The software in that room isn't "legacy" in the way we use the word.  It's battle-tested in a way most of our software never will be.

At [Simple Thread](https://www.simplethread.com/) we build software for the energy industry — another domain where the stakes are real and the existing systems exist for reasons that aren't always obvious from the outside.  That tower visit made me ask a question I keep coming back to: are we bringing the same humility to our work that this environment demands?

Not as a source of anxiety.  As a discipline.  A reminder that understanding the system you're replacing is as important as building the one that comes next.

## What to Carry Forward

Before you open your laptop, understand what the existing system is actually doing.  Not what the requirements doc says it does.  What it *actually* does.  The annotations in the margins.  The shift-change rituals.  The meaning encoded in physical position, in muscle memory, in decades of accumulated practice.

Resistance to change isn't a user problem to overcome.  It's a signal worth decoding.  When experienced professionals push back on your shiny new system, the most productive thing you can do is shut up and ask why.

The boring-looking software in that tower cab isn't a failure of imagination.  It's evidence of respect for the domain.  And that might be the most important design principle I've ever seen demonstrated.
