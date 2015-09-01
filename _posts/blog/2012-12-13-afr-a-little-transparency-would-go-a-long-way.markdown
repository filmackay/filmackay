---
layout: post
title: "AFR: A little transparency would go a long way"
date: 2012-12-13
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
[http://adeleferguson.com/ Adele Ferguson] wrote a [http://www.afr.com/Page/Uuid/8167883c-4533-11e2-9c73-817ba4ddc986 not-bad piece] on the removal of broker ID's from the Australian equities market back in 2005.

One aspect of the story she didn't mention was the fact that pre-2005 only brokers could see the ID's (at least in theory). This created information asymmetry, which the brokers did not mind, since their clients would need to constantly ring them to find out the identity of orders they were interested in. Fixing this gap was certainly a positive.

At the time I felt against the "large investment bank" push to ban real-time ID's. But, I appreciated the fact that they were more of a "sitting duck" of "showing their hand" in allowing competitors to see what they were doing in real-time. Personally, I think their self-interest should lead them to act less predictably, but that's a story for another post.

Instead, I advocated (and still do) for choice. Let each broker decide whether their ID is displayed ("leaked") in real-time or not. Not only on a per-broker basis, but on a per-order basis. Giving the decision on a "all-in" basis to the regulator, I thinks makes no sense. ASIC steers well clear of making other less sensitive decisions on behalf of participants, why make this one?

Some brokers want disclosure - for example small cap stock traders want everyone to know they are behind a certain order with the view of getting other clients to contact them directly in order to assemble deals. I guess one wrinkle (and perhaps a reason the ASX is happy blanket with non-disclosure), is that it could use the lit market to advertise for business in dark pools. Not such a raw nerve in 2005.

I am currently doing some work on trade analytics to measure the effect of HFT and smart algos in figuring out what the investment banks are doing. There is a significant amount of leakage here, and that is without real-time broker numbers. Re-introducing them (this time for everyone presumably?) would make it a whole lot worse for them, as the algos would more precisely be able to track their most probable actions. Allowing the broker to choose his disclosure I think balances the dual interests of privacy (we don't want another incentive to move to dark/fragmented venues) and disclosure (some people want their ID broadcast).

I would say, for example, if [http://www.iress.com.au IRESS] wanted to distribute broker ID's for those clients who wanted them broadcast - why should (could?) ASIC stop it? (I suggested this possibility in 2005 and it was met with a "we would not be amused" rebuke). But, disclosure *should* belong to the order-owner, not to the regulator.

Much of this issue comes back to the question: who owns the data? Do exchanges, or even ASIC have the right to mandate what you //can't// say about your order? I've consistently argued that the "liquidity provider is king": and more control should be given to these participants a-la my [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}) proposal. Allow them to control their orders, and they'll be less likely to want to leave and trade in the dark, thereby harming the public benefit via fragmentation. Many of the inefficiencies in the market today are, I would argue, as a result of the lack of control that liquidity providers have over their orders.

Finally, some amusing contradictions:

> The argument at the time to support the removal of broker IDs was that the big broking firms felt they were at a disadvantage when trading because it encouraged front running.

Front running is acting on privileged client order information. You can't front-run on public information. Exploiting someone's predictability in the way they trade, is something else entirely.

> But since it removed broker numbers from the trading screen, it took away what many traders and investors considered an important piece of information in trying to predict where share prices might go. It can be argued that it spawned the quest for less and less transparency

One man's front running, is another's important piece of predictive information? Two sides of the one coin.
