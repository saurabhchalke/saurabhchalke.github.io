---
title: "Catching Lightning in a Bottle"
layout: post
date: 2025-09-07
categories: [Weather, Energy, Innovation, Sustainability]
published: true
---

There are only a few moments when you know, while it’s happening, that you’re in the room for something that might be a real breakthrough. It doesn’t happen every day. This week felt like a small milestone for us, quiet but important. I want to capture a few thoughts while they’re still fresh.
> TL;DR: in tests, we can reliably control our high‑altitude balloons, hold altitude, and autonomously steer to a target location. Early results suggest they can survive for months and collect on the order of 1,000× more data than many current systems, at lower cost and higher resolution than satellites or drones.

<p style="text-align:center">
  <img src="{{ '/assets/images/catching-lightning-in-a-bottle/latest-launch.jpeg' | relative_url }}" alt="Latest launch of our high-altitude balloon system" style="width:80%; height:auto;">
</p>

<p style="text-align:center; margin: 0.25rem 0 1rem;">
  <a href="https://youtu.be/M6fSuUqmJyI" target="_blank" rel="noopener" style="font-size:0.9em;">Watch the launch video</a>
</p>

This isn’t a polished write‑up; it’s a quick attempt to capture the ideas while they’re still warm.

### Progress Isn’t Linear

The nature of scientific progress may look like a smooth, linear curve from the outside, but from the inside it’s anything but: long periods of frustration and dead ends punctuated by sharp steps forward. Most approaches failed, but the ones that worked did so spectacularly enough to make the whole process worth it.
  
To get the really good ideas, we need to tolerate some bad and wacky ones. I keep reminding myself about the lesser‑known aspects of Newton’s life. In addition to the work Newton is best known for, he also studied alchemy (the British authorities banned work on this because they feared the devaluation of gold) and considered himself specially chosen by the Almighty for the task of decoding biblical scripture[^1]. Alchemy and theology “research” accounted for more than two‑thirds of Newton’s life, more than physics and math.

You can’t know which wacky ideas will turn out to be right, and nearly every breakthrough starts out sounding like a terrible idea. The only reliable stance is to stay self‑aware, keep your ego small, try to be less wrong every day, and do the work with care and love (especially on physics‑heavy, non‑incremental bets).

> "Cherish those who seek the truth but beware of those who find it" - Voltaire

### Experiments On The Edge

I like to keep reminding my wonderful team that when you're on the bleeding edge, both outcomes of any experiment, pass or fail, are still good outcomes as far as I can tell. If it works, we get closer to building a really valuable piece of future infrastructure, and if it fails, best case scenario we find gaps in our current understanding of physics (which may well be Nobel Prize‑worthy), and in the worst case we correct errors about ourselves, our team, and our process.
Truth‑seeking (which might as well be a synonym for science) is a painful but incredibly virtuous pursuit.

When referring to the success of our latest launch test, I like to say breakthroughs, but it has been a series of smaller multidisciplinary breakthroughs in hardware, materials science, and flight autonomy software, each one building on the last.

I feel extremely proud of the tech the team has pioneered (and I’m optimistic about pushing it much further). Our current prototype system now weighs less than a kilogram. It surprises me (even as I type this) how much we've managed to miniaturize the hardware.
As much as I'd love to get into the technical details, we're embargoing a lot of our secret sauce until peer review (and patent filings).

### Why This Matters

> “Don’t fight the business equivalent of the laws of physics.” - Sam Altman

It's easy to get nerd‑sniped by interesting puzzles and lose sight of the bigger picture. I’ve been guilty of this many times, and I probably will be again. But if there is one important “business lesson” I’ve internalized, it’s that you create real value by doing useful things people want (time saved, money earned, risk reduced, capability unlocked) and doing them at scale. You could even make a 2×2 of useful vs. not useful, and scalable vs. not scalable, and you’ll see the most valuable companies in the top‑left quadrant.

|                     | **High scale**                                                                                                                                                  | **Low scale**                                                                                                                                                  |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **High usefulness** | Space; AI; Chips; Clean Energy; Vaccines. | Therapies for rare diseases; traditional higher‑ed; libraries & cafes. |
| **Lower usefulness**   | Modern social media; video games; cannabis; fast fashion.                     | Certain corners of high‑frequency finance; speculative crypto; rent‑seeking. |

Seen this way, it can feel discouraging to watch so many smart people chase things that aren't very useful for the world. There are many urgent problems to solve, and in my view deep‑tech startups are one powerful way to tackle them.

The [efficient market hypothesis](https://en.wikipedia.org/wiki/Efficient-market_hypothesis) is often overstated and misapplied. Believing it too literally has pulled a lot of smart people into Wall Street and ad tech, but I know firsthand[^2] there’s still plenty of zero‑to‑one[^3] value in the physical world, and when you unlock it, society tends to make room for it.

This was a long‑winded way to say we’re building future physical infrastructure aimed at being maximally useful and maximally scalable.

### Problems We’re Focused On

Some concrete problems our systems aim to help with:

- India launches just 39 [radiosondes](https://en.wikipedia.org/wiki/Radiosonde) a day; they’re expensive and single‑use. They go up for a few hours, then come down. We’re building a system that can stay aloft for months and, in specific contexts, capture roughly 1,000× more data than the state of the art, while beating satellites and drones on cost and resolution.
- Renewable production is intermittent and unpredictable, and generators face fines for missing delivery windows. We’re building systems that predict production and consumption in real time and help balance the grid.
- Air pollution is a huge problem in India. Current air quality models need boundary-layer height and vertical chemistry; surface-only networks can’t capture mixing heights/ozone lofting.
- Many aerospace and aviation companies struggle with modeling the upper atmosphere because there’s almost no data in the stratosphere.
- There are many more in insurance, agriculture, defense, and beyond.

### Ideas For Others To Build

If you’re still reading, here are a few deep‑tech ideas we’re not pursuing but would love to see others take a stab at:

- Batteries that survive extreme temperatures. We currently have a [Rube Goldberg machine](https://en.wikipedia.org/wiki/Rube_Goldberg_machine) for thermal management of lithium polymer batteries in our system, but it is far from ideal. I am sure there is a better way to do this.[^4]
- Domestic helium production in India. We currently import helium and it’s expensive. There’s likely a way to do it cost‑effectively here[^5].
- I feel a lot of humanoid robotics is overrated, but dexterous humanoid hands are extremely underrated. We discount how much evolution has gone into the human hand. We do most of our hardware manufacturing ourselves and could definitely use an extra pair of robotic hands for assembly.
- Stratosphere‑grade materials. I can’t share too much, but we’re innovating a lot in materials science, and I’ve found India’s current materials industry isn’t up to the task (if there’s one problem we might solve in‑house, it’s this).

If you are interested in what we're building here, please feel free to reach out.

### Where We Are Now

We are very much still in the first innings, but as a deep‑tech startup, one of the biggest risks we face is that the underlying tech is so hard the product never gets built. I feel fortunate to have de‑risked this core technical risk, and I’m excited to see where this goes. We are still a long way from being “production‑ready,” but we have a lot of confidence that we will get there.

Our balloons operate in the stratosphere, brutal territory with −80 °C temperatures, violent daily heating and cooling, and 150+ kmph wind shears near the tropopause that can shred the balloon envelope. It’s a hard place to run anything in production.

Our edge comes from long duration and ultra‑low cost. With appropriate safeguards, we aim to operate large fleets at a fraction of the cost of traditional weather satellites. The data we collect can help improve AI weather models which, in some settings, are beginning to outperform today’s best supercomputer forecasts. Coverage in data‑sparse regions may be especially useful.

### Rebrand

P.S. Speaking of rebranding, I wasn’t a big fan of our previous name, and the team spent more time than I’d like trying to come up with a new one. I’m happy to share that we’ve settled on: “Thinking Balloon.” I think the name captures the essence of what we’re trying to do and how we’re going about it.

(Take a look at our new website: [thinkingballoon.com](https://www.thinkingballoon.com))

<p style="text-align:left">
  <img src="{{ '/assets/images/catching-lightning-in-a-bottle/logo.png' | relative_url }}" alt="Thinking Balloon Logo" style="width:120px; height:auto; float:left; margin: 0 0.75rem 0.5rem 0;">
</p>

(One of my primary personal criteria for the name was: if Richard Feynman were alive today, would he put our sticker on his laptop? I like to think he would.)

We don’t have all the answers, and we’ll make mistakes. If you see blind spots, technical, ethical, or otherwise, I’d love to hear from you.

### Footnotes

[^1]: We may see a resurgence of alchemy and theology as we approach technological singularity, unlock material abundance, and face the existential questions that come with it.

[^2]: One often‑overlooked cheat code: you can get to the bleeding edge of almost any field by reading a dozen great books. I’ve used it several times: Zero‑Knowledge Proofs, VR, caching, and now autonomous systems in aerospace.

[^3]: One book that I highly recommend to people working in the frontier (whether that's engineers, grad students, or artists) is "[When We Cease to Understand the World](https://en.wikipedia.org/wiki/When_We_Cease_to_Understand_the_World)" by Benjamin Labatut. It is a collection of short stories about the lives of some of the greatest scientists in history, and how the road to scientific progress can get quite lonely and is often paved with grand delusions, obsessions, and madness.

[^4]: Much of quantum computing is hype, but if there’s one near‑term payoff, it’s materials simulation: discovering new materials that could dramatically improve battery technology.

[^5]: Helium is non‑renewable and reserves are shrinking. We plan to move to hydrogen in the medium term, but it’s not as easy as it sounds and there are many challenges. If fusion arrives sooner than expected, helium becomes a byproduct, so long‑term shortages likely ease.
