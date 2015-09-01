---
layout: post
title: "A New Model for Understanding High Frequency Trading"
date: 2013-06-11
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
I have found the term High Frequency Trading to be somewhat overloaded, and now unusable term. Instead of referring to high-tech traders, the terms is now referring to more traditional traders who are dragged into the technology war in order to protect themselves. To throw both of these groups under the one "HFT" label is to completely misunderstand what is going on. I would like to propose a model for HFT that splits the term into 4 subcategories:

# Classes of HFT:

* **Market Making**: automated quoting of prices in order to earn the bid/ask spread
* **Algorithmic Execution**: automated and (hopefully intelligent) splitting up of a parent order into a number of child orders, in a way that avoids detection by the two following categories.
* **Statistical Arbitrage**: the use of statistical models to make short-term predictions about where prices are going to move. By trading profitably they make the market (according to academics) "more efficient", but they can also be predatory by figuring out likely parent orders of the previous category.
* **Ultra-low Latency**: this category relies only on speed, and in the absence of quote stuffing (read: in Australia) are aggressive traders who take liquidity before anyone else can. As such they can be considered predatory by driving up the cost of execution to other traders.

Of course the only remaining category on this list to describe the entire market is: humans.
It is unfortunate that the press, regulators and folklore have type-cast these four communities under a single heading. Just like trying to describe a place, or a race of people under a single stereotype – so to thinking about HFT in it’s entirely is somewhat meaningless. It is uninteresting in the extreme to talk about the commonalities of a broad populations of people, which is exactly what the recent [ASIC report did](http://www.asic.gov.au/asic/asic.nsf/byheadline/13-052MR+ASIC+reports+on+dark+liquidity+and+high-frequency+trading?openDocument) for HFT. No wonder they didn't find much.

Looking inside this very broad community is far more interesting. Under the HFT banner there is both predator and prey. Each of the categories outlined above has a very different mix of motivations, techniques; and therefore implications for the market. Some categories (like Algorithmic Execution) are often only employed because they’re forced to, in order to try to protect them against other more informed HFT’ers. They’re not the ones to look at in order to find causality.

Let’s focus on the most misunderstood, perhaps unknown, of these categories: ultra-low latency. These are not the “HFT” firms like [Optiver](http://www.optiver.com.au/) who provide quotes to the media, that we are supposedly meant to take as somewhat representative of the whole HFT population. Instead, ultra-low latency specialists with one capability: speed. Nowadays, everyone under the HFT umbrella thinks they are "low-latency", since they think they are fast. I’m not talking about them, but rather the ones that dedicate themselves to being fast. The difference between low-latency and "ultra low-latency" is that the latter are the fastest.

When I say fast, I mean incomprehensibly fast. To be the fastest firm in the market to make a trading decision and send an order, you would need to be able to act within 5 micro-seconds. To put that in perspective it takes a 747 jet travelling at top speed (say 1,000 km/h) this long to travel 1.5 millimetres. Your LCD monitor will probably not be able to update itself and show this decision for another 2 meters. The technology used to employ this speed has gone beyond computer “servers” in any sense you would recognise. In contrast to what you may think: immense servers with banks of flashing lights, they instead use specialised [FPGA](http://en.wikipedia.org/wiki/Field-programmable_gate_array) chips which are essentially tiny hard-wired computers that are only capable of performing one task: trading. There is no hard disk or operating system, screen, mouse or keyboard – just a network port. Anything not directly relating to making a trading decision is stripped out - who needs it. Forget Windows or Linux there is no operating system to slow things down – the program is hard-wired into the chip.

Whilst being really fast is important – it is just a means to the real end objective: to be faster than the other guy. And being the fastest is not just about having great technology - there are another aspects that dictates the pace: such as compromise. If you are competing with another trader (and no doubt you are) who also has the latest technology you do, but they are just a bit more motivated than you to being the fastest – they still have an angle. Here is where the risks checks come in. Two traders with identical technology then inevitably get into a reverse auction on risk checking, as each risk check (or even [sanity check](http://en.wikipedia.org/wiki/Sanity_testing)) comes with a cost.

What we have now is a market that rewards the fastest traders with profit, since they are able to beat their competition to the punch. In order to be the fastest these traders have the perverse incentive to reduce the number and quality of their risk checks. Since every “risk check is slowing you down” – it is akin to a car race where helmets are not standardised. It would not be a suprise to see them to get lighter, and smaller. If you are in this game you have no choice to play along – join them or go out of business. This is why car racing has safety standards that cannot be compromised. Someone would notice if drivers got into a car without a helmet - in electronic markets we have no such visibility of the software employed by trading firms. We only find out what was going on after a crash.

As an aside: the idea that “kill switches” (as proposed by ASIC) can prevent any issues created at this scale of time simply does not make any sense. These mechanisms will always arrive too late.
