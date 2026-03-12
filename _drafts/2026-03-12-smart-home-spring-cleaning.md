---
layout: post
title: "Smart Home Spring Cleaning"
date: 2026-03-12
---

Spring cleaning usually means clearing out closets and wiping down baseboards.  This year I'm doing something different.  I'm auditing every "smart" device in my house and figuring out what stays, what goes, and what never should have been plugged in to begin with.

![A sketch of smart home devices — Philips Hue bulbs, a robot vacuum, Nest doorbell, Amazon Echo, Apple TV, and a Wyze camera — piled together](/assets/images/smart-home-devices.png)

## Taking Inventory

I grabbed a notebook and went room by room.  Here's what I found:

- 14 smart bulbs (three different brands, because apparently I have no loyalty)
- 2 smart plugs
- 3 voice assistants (two Echos and a HomePod Mini I forgot existed)
- 1 smart thermostat
- 2 smart locks (the garage one has literally never worked)
- 1 robot vacuum
- 4 cameras (Ring, Wyze, and a random Eufy someone gave me as a gift)
- 1 smart smoke detector
- A drawer full of sensors and bridges I stopped using months ago

That's over 25 devices.  Eight manufacturers.  Four apps.  Three voice ecosystems.  God knows how many cloud services keeping it all alive.  This is what four years of "it's only $30" gets you.

## How the Clutter Piled Up

None of this happened all at once.  That's the problem.  Every single purchase felt reasonable at the time.  The Wyze cam is only $30.  The smart plug means coffee is ready when I wake up.  The thermostat will pay for itself in energy savings.  Sure it will.

It's the same way junk drawers happen.  One battery, one takeout menu, one mystery cable.  You never decide to fill a drawer with crap — it just accumulates.  My smart home is a junk drawer spread across every room in the house.

Every new device is another app, another firmware update, another account with a password, another privacy policy you didn't read, another cloud service that could shut down tomorrow.  The overhead isn't in any single device.  It's in the pile.

## The Compatibility Mess

My Hue bulbs talk to HomeKit.  My Ring cameras are locked to Alexa.  The Wyze stuff lives in its own universe.  The thermostat works with Google Home, which I don't even use anymore.  The robot vacuum "supports" all three assistants but works reliably with none of them.

I tried building automations — "when I leave the house, lock the door and turn off the lights" — and it requires duct-taping three platforms together with IFTTT.  Half the time it works.  The other half, I come home to every light on and an unlocked front door.  Fantastic.

[Matter](https://csa-iot.org/all-solutions/matter/) was supposed to fix all of this.  Maybe it will eventually.  Right now I've got exactly two Matter-compatible devices and the setup process was no better than anything else.

## What It All Cost

Before I could decide what to toss, I needed to see the damage.  I finally did the math I'd been avoiding.

| Device | Qty | Unit Cost | Subscription | Annual Sub |
|--------|----:|----------:|--------------|----------:|
| Philips Hue bulbs | 9 | $50 | — | — |
| LIFX bulbs | 3 | $45 | — | — |
| Sengled bulbs | 2 | $10 | — | — |
| Hue Bridge | 1 | $60 | — | — |
| Smart plugs (TP-Link) | 2 | $15 | — | — |
| Echo Dot | 2 | $50 | — | — |
| HomePod Mini | 1 | $99 | — | — |
| Nest Thermostat | 1 | $130 | — | — |
| August Smart Lock | 1 | $150 | — | — |
| Yale Smart Lock | 1 | $120 | — | — |
| Roborock vacuum | 1 | $400 | — | — |
| Ring Doorbell | 1 | $100 | Ring Protect | $40 |
| Ring Indoor Cam | 1 | $60 | (bundled) | — |
| Wyze Cam v3 | 1 | $36 | Cam Plus | $24 |
| Eufy Indoor Cam | 1 | $40 | — | — |
| Nest Protect | 1 | $120 | — | — |
| Sensors/bridges (misc) | — | ~$150 | — | — |
| **Total** | | **~$2,040** | | **$64/yr** |

Over two grand.  Plus $64 a year just to store cloud footage I almost never look at.  Seeing it in a table like that hit different than I expected.

But that table was just the hardware and the subscriptions I knew about.  I hadn't looked at what I was actually being *billed* yet.

## The Subscription Audit

I pulled my transaction history from Lunch Money going back to January 2024.  Two years of smart home spending, laid out in a spreadsheet.  Here's what I found:

| Service / Purchase | Status | Total Spent | Monthly | Notes |
|---|---|---:|---:|---|
| SimpliSafe monitoring | Active | $607 | $13.20 | Was $32/mo — downgraded Apr 2025 |
| Wyze Cam Plus | Cancelled | $293 | — | Billed through Apple for 21 months |
| Apple iCloud+ | Active | $46 | $2.99 | Upgraded for HomeKit Secure Video |
| Wyze hardware (4 orders) | — | $361 | — | Cameras + doorbell, Jan 2024–Apr 2025 |
| **Total** | | **$1,307** | **$16.19** | Peak was ~$30/mo before cuts |

$1,307 in two years.  On top of the hardware I'd already bought.  And I only found half of this because I went looking.

**The hidden Wyze bill.**  This one still bothers me.  Wyze Cam Plus was billing $13.93/mo through Apple's App Store.  In my finance app, every charge showed up as "APPLE.COM/BILL" — no mention of Wyze anywhere.  Lunch Money tagged it as "Apple TV+" for almost its entire life.  I paid $293 over 21 months for a cloud recording service I forgot I'd subscribed to.  I only caught it when I dug into Apple's subscription management during this audit.

**The downgrade I never thought to do.**  SimpliSafe had been charging me $29.99/mo since I set it up, which later bumped to $31.99/mo.  I never questioned it.  When I finally looked at the plan tiers, I realized I was paying for interactive monitoring and features I wasn't using.  Dropped to the $13.20/mo plan and saved roughly $230 a year.  Just like that.  The money was there the whole time — I just never looked.

**The hardware trap.**  I spent $361 on Wyze cameras and a doorbell over the past two years.  Without the Cam Plus subscription, those cameras lose cloud recording, person detection, and event clips.  The hardware is a sunk cost that creates pressure to keep paying.  Cancel the subscription and you've got a $100 camera that records to a microSD card you'll never check.

At various points over the past two years, I've had active services across SimpliSafe, Wyze, Apple HomeKit, and Google Nest.  Four apps, four accounts, four billing channels, four cloud backends.  Each one a small monthly line item that's easy to ignore individually and exhausting in aggregate.

## What's Getting Tossed

Spring cleaning means making cuts.  Here's what's leaving:

- **The HomePod Mini.**  It's been in a closet for six months.  I forgot it existed until I literally found it during this audit.  Gone.
- **The Yale garage smart lock.**  It has never worked right.  Not once.  Going back to a dumb deadbolt.  Sometimes dumb is better.
- **The Eufy camera.**  I don't even remember setting it up.  I think it's been recording my hallway to a microSD card that's probably full.
- **Wyze Cam Plus subscription.**  $293 over 21 months, billed through Apple where I couldn't even see it.  Cancelled.  The cameras will survive on local storage.
- **The IFTTT automations.**  All of them.  They're unreliable and I spend more time fixing them than they've ever saved me.
- **The drawer of sensors and bridges.**  If I haven't touched it in six months, it's e-waste.

## What's Staying (With Conditions)

Not everything is getting thrown out.  Some of this stuff actually works.  But I'm consolidating.

- **Philips Hue bulbs + Bridge.**  They work.  They're reliable.  They talk to HomeKit natively.  The LIFX and Sengled bulbs are getting replaced with more Hue over time.  One bulb brand.  One app.
- **Nest Thermostat.**  It does its job and the energy reports are genuinely useful.
- **Ring Doorbell + Indoor Cam.**  I don't love being locked into Amazon's ecosystem, but the doorbell works well and the subscription is already paid.  This stays until something better comes along.
- **Roborock vacuum.**  It vacuums.  I don't need it to be smart.  I just press the button.
- **August Smart Lock (front door).**  Actually reliable.  Works with HomeKit.  Stays.

## The New Rules

Going forward I'm setting a higher bar.  Before anything new comes into this house:

1. **It has to support Matter or HomeKit natively.**  No adapters, no Docker containers, no "it works if you also run Home Assistant."
2. **It can't require a subscription to be useful.**  If the cloud goes down and the device becomes a brick, I don't want it.  I'm not paying $14/mo to store footage I never watch.
3. **Audit subscriptions every six months.**  If I'd done this a year ago I would've saved over $500 between the SimpliSafe downgrade and the Wyze cancellation alone.
4. **One ecosystem.**  HomeKit as the primary, [Home Assistant](https://www.home-assistant.io/) as a bridge for the holdouts.  That's it.  No more three-app juggling.
5. **Some things just don't need to be smart.**  My toothbrush does not need Bluetooth.  My smoke detector does not need to send me push notifications to tell me its battery is fine.  Stop it.

## The Point

Your smart home probably needs spring cleaning too.  Not the "wipe down the Echo" kind.  The real kind.  Walk through your house with a notebook.  Count the devices, the apps, the accounts, the ecosystems.  Write down what actually works and what you're just... maintaining.

The number will surprise you.  And then you can start throwing things away.

That's the best part of spring cleaning anyway.
