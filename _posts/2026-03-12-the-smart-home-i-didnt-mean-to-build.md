---
layout: post
title: "The Smart Home I Didn't Mean to Build"
date: 2026-03-12
---

It started with a lightbulb. A single Philips Hue bulb that I bought on a whim at Best Buy because it was on sale and I thought it'd be fun to turn my desk lamp purple. That was four years ago. Last weekend I sat down and tried to inventory every "smart" device in my house, and the list genuinely startled me.

## The Audit

I grabbed a notebook and walked room by room. Here's the rough count:

- 14 smart bulbs (across three different brands)
- 2 smart plugs
- 3 voice assistants (two Echos, one HomePod Mini that I forgot I owned)
- 1 smart thermostat
- 2 smart locks (one on the front door, one on the garage that's never worked right)
- 1 robot vacuum
- 4 cameras (Ring, Wyze, and a random Eufy I got as a gift)
- 1 smart smoke detector
- A drawer full of sensors and bridges I stopped using

That's over 25 devices from at least eight different manufacturers, running across four different apps, connected to three different voice ecosystems, and dependent on who-knows-how-many cloud services to function.

## The Slow Drip

None of this happened all at once. That's the thing. Each device felt like a reasonable, self-contained purchase at the time. Oh, the Wyze cam is only $30. The smart plug makes the coffee maker start before I get out of bed. The thermostat will pay for itself in energy savings within a year.

But nobody warned me about the compound effect. Every new device adds another app to manage, another firmware to update, another account with a password, another privacy policy I didn't read, another cloud service that could shut down or get acquired. The cognitive overhead isn't in any single device — it's in the aggregate.

## The Fracture

What really hit me during the audit was how *fractured* everything is. My Hue bulbs talk to HomeKit. My Ring cameras are locked to Alexa. The Wyze stuff has its own universe. The thermostat works with Google Home, which I don't even use anymore. The robot vacuum technically supports all three assistants but is reliable with none of them.

I tried building automations — "when I leave the house, lock the door and turn off the lights" — and it requires stringing together three different platforms with IFTTT as duct tape in the middle. Half the time it works. The other half, I come home to lights blazing and an unlocked door.

Matter was supposed to fix this. And maybe it will, eventually. But right now I've got exactly two Matter-compatible devices and the setup process was no easier than anything else.

## The Real Cost

The dollar cost is one thing — probably north of $2,000 across all of it, though I've never wanted to do that math precisely. But the real cost is attention. Every few weeks something breaks. A bulb goes "unreachable." A camera goes offline. A firmware update changes the UI of an app I'd finally gotten used to. I spend time troubleshooting things that are supposed to be making my life *easier*.

And there's a psychological weight to it, too. I've become the IT department for my own house. My partner asks me why the bedroom lights won't turn on, and I'm SSH-ing into a Raspberry Pi running Home Assistant at 11pm on a Tuesday trying to figure out why a Zigbee bridge lost its pairing.

## What I'm Doing About It

I don't have a grand plan. But the audit itself was clarifying. I'm starting by:

- **Picking one ecosystem and committing.** I'm leaning toward HomeKit + Home Assistant as a bridge for non-native stuff. One control plane.
- **Removing devices I don't actually use.** That HomePod Mini in the closet? Gone. The garage smart lock that never worked? Going back to a dumb deadbolt.
- **Setting a higher bar for new purchases.** Before I buy anything, it needs to support Matter or HomeKit natively. No more "it works with an adapter if you also run this Docker container."
- **Accepting that some things don't need to be smart.** My toothbrush does not need Bluetooth. My smoke detector does not need to send me push notifications to tell me its battery is fine.

## The Takeaway

The smart home industry has a marketing problem disguised as a compatibility problem. Every device promises simplicity in isolation and delivers complexity in combination. The slow drip of acquisition means you never have a moment where you step back and see the full picture — until you force yourself to.

If you've been accumulating devices for a few years, I'd recommend doing your own audit. Walk through your house with a notebook. Count the apps. Count the accounts. Count the ecosystems. The number will probably surprise you.

And then ask yourself: is this actually making my life simpler?
