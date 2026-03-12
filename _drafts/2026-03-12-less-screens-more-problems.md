---
layout: post
title: "Less Screens, More Problems"
date: 2026-03-12
---

I've been trying to use fewer screens.  Everyone says you should.  Put the phone down.  Close the laptop.  Be present.  Touch grass.  I get it.  I agree with it.  I'm terrible at it.

The problem isn't willpower.  The problem is that screens are where all the useful information lives.  Weather.  Calendar.  To-do list.  Whether my kid's school is delayed.  My smart home status.  Package tracking.  The stuff I actually need to know to function as a human being in 2026.

So every time I try to "use fewer screens," what actually happens is I pick up my phone to check the weather and 25 minutes later I'm reading a Reddit thread about someone's home lab setup.  The screen isn't the problem.  The internet behind the screen is the problem.

## The Phone Trap

My phone is simultaneously the most useful and most destructive object I own.  I need it for two-factor auth, for messaging, for maps, for checking whether it's going to rain before I walk the dog.  Legitimate, boring stuff.

But the phone doesn't let you do just the boring stuff.  You unlock it to check the temperature and your brain goes: notification badge on email, oh let me check that, while I'm here let me look at Slack, oh someone posted something interesting, let me open the link, and now I'm reading an article about the geopolitics of semiconductor manufacturing and it's been half an hour.

Every "quick check" is a slot machine pull.  Sometimes you get the weather and put it down.  Most times you don't.

I tried the grayscale accessibility trick.  I tried Screen Time limits.  I tried putting my phone in another room.  All of these work for about three days before I find a reason to override them.

## What I Actually Want

What I want is dead simple.  I want a surface in my house that shows me information without giving me the option to fall down a hole.  A thing I can glance at — like a clock or a thermostat — that tells me what I need to know and nothing else.

No browser.  No notifications.  No apps.  No infinite scroll.  Just... data.

I looked into a few options.  A dedicated tablet mounted on the wall running a dashboard.  But that's still a screen with a browser, and I know myself.  A smart display like the Echo Show.  But Amazon's idea of "helpful information" is 40% ads for things I already bought.  A whiteboard.  Seriously considered it.  But I'm not going to manually update the weather on a whiteboard every morning.

## Then I Found TRMNL

[TRMNL](https://usetrmnl.com/) is this little e-ink display that sits on your desk or mounts on your wall.  It connects to Wi-Fi, pulls data from a bunch of sources, and just... shows it.  That's it.  No touchscreen.  No browser.  No app store.  It refreshes every few minutes and displays whatever you've configured.

E-ink is the key part.  It looks like paper.  It doesn't glow.  It doesn't demand your attention the way a backlit LCD does.  It just sits there, quietly being useful.

You set it up with plugins — weather, calendar, Hacker News headlines, GitHub activity, smart home status, custom API data, whatever — and it cycles through them.  Or you pin one screen.  Your call.

I've had mine for about a month and it's the closest thing I've found to "information without temptation."

## Why It Works (For Me)

The reason it works isn't the technology.  It's the constraints.

You can't browse the web on it.  You can't check email.  You can't "just quickly" open anything.  There is no rabbit hole.  It shows you a thing, and then you walk away.  The interaction model is the same as looking at a clock on the wall.  You glance, you get the info, you move on.

I have mine set up to rotate through:

- Weather forecast for the day
- My calendar
- Hacker News top 5 (headlines only, no links to tap)
- A random quote (my partner's favorite)

That covers about 80% of the reasons I used to pick up my phone in the morning.  Now I just look at the little e-ink screen on my kitchen counter while I make coffee.  No unlock.  No notifications.  No slot machine.

## It's Not Perfect

A few honest complaints:

- **The refresh rate is slow.**  It's e-ink, so it takes a few seconds to update and there's that ghosting flash when it transitions.  This isn't a real-time display.  If you need up-to-the-second data, this isn't it.
- **Plugin selection is still growing.**  Some integrations I wanted aren't there yet.  I ended up writing a custom one to pull my Home Assistant data, which was fun but not everyone is going to do that.
- **It's another device.**  I'm aware of the irony here given my smart home spring cleaning post.  But at least this one replaces screen time instead of adding to it.

## The Bigger Point

I don't think the answer to "too many screens" is "no screens."  That's not realistic for most people.  The answer is screens that know their place.  Screens that give you what you need and then shut up.

TRMNL isn't the only way to do this.  There are other e-ink displays out there.  You could build your own with a Raspberry Pi and an e-paper HAT if you're into that.  The specific product matters less than the idea: put useful information on a surface that doesn't try to steal your attention.

We figured this out with clocks centuries ago.  A clock tells you the time.  It doesn't also try to sell you a watch or show you what time it is in 30 other cities or suggest you might be interested in sundials.  It just tells you the time.

That's what I want from more of my technology.  Tell me the thing.  Then leave me alone.
