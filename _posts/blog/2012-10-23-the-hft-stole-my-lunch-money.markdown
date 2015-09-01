---
layout: post
title: "The HFT Stole My Lunch Money"
date: 2012-10-23
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
# Perspective

When talking about HFT, it’s important we get this problem in perspective: predatory HFT is not to blame for taking that stock you bought for $2, ending up at 20c a few months later. I was reminded of this by a mate (who knows retail traders very well) who said HFT is a long way from the biggest problem faced by retail traders. Lack of knowledge and information that comes through established private networks would be higher on this list. Predatory HFT is akin to a “rounding” loss for retail traders, and only directly exposes you when you trade, not hold, securities.

Nonetheless, a rounding loss for an individual, when aggregated, can be substantial enough to worry about when it comes to the entire market. We just need to keep it in perspective and not blame all manner of things on HFT. My current concern is that the term “high frequency trading” is being defined as “everything about the market I don’t like”. Not a definition that’s going to help in identifying and solving the issues.
I do feel there is a predatory class of computerised traders that are not improving liquidity or providing any value to the marketplace. But this is only a subset of the traders that are currently being scrutinised. It therefore makes sense that we look to understand it, before making wild assertions about what the regulators “should do about it”.

# Public Opinion

I’ve been on holidays for the last month touring around country NSW and southern Victoria, and reading the flow of press articles about HFT en route. What started out as a dribble has now turned into a torrent. There is a confusion, as most of the content published on HFT is not based on any knowledge – but rather prejudice and fear. It is deeply polarised, though the ratio of pro v anti-HFT rhetoric has shifted heavily from the former to the latter. HFT now has a PR problem, being found guilty in the court of public opinion; we are just not sure what the charges are.

On the ASX today we have had an explosion of algorithmic traders (“AT”). The fastest set of these AT’s we’ll refer to as high frequency traders (“HFT”). Everyone is getting these two confused. They are quite different animals and we need to understand the difference in their objectives, and operation. [Optiver](http://www.optiver.com.au/) is often quoted in the press as the canonical instance of an HFT firm; however I would argue it is not an HFT firm at all. They are an AT for sure, being in the business of highly automated market-making and using sophisticated mathematical algorithms. They also seem very fast to a human (I’d guess a reaction speed of 0.0001 seconds), but that is actually not fast enough (in my view) to be defined as HFT. For mine, the essence of HFT is all about being at the front of the speed rate – whatever speed that requires. Quite simply, Optiver are not the fastest guys in the room – their strategies rely on sophisticated intelligent algorithms that are just too slow to win the outright speed race. I would argue the current benchmark for an HFT firm in Australia is to be able to trade faster than 0.00001 seconds. That may not seem like much difference to you – but in human terms think of Usain Bolt racing someone who can only manage to run the 100M in a minute or two; not much of a race!

The real risk in the current debate on “HFT” is that we confuse HFT with AT. What makes HFT dangerous is exactly the thing that separates it from other AT’s: speed. To achieve speed, you need to sacrifice smarts. Winning the speed race (remember there is no silver medal in this financial race) involves giving up everything to achieve it. That includes flexibility, sanity checks, and verification steps. The kinds of things that help prevent “run-away algorithms” such as Knight Capital. Speed is a cruel master, and requires complete devotion. What you end up with is an algorithm that is the fastest in the market, but is also very, very, fragile. By rewarding those in the market who are the fastest (through the price-time priority market rules) you are essentially encouraging behaviour that leads to volatility.

Think of a group of HFT firms – who are all in the running to be the fastest on any given trade: each has only the very minimal intelligence programmed into their algorithm; otherwise they wouldn’t be in the race in the first place. When these algorithms start triggering one another, they can create massive price volatility; the kind of volatility that is now a daily occurrence on the US markets. These “flash spikes” form a nuisance for retail traders in triggering stop losses, trading halts, and the risks associated with partial cancellation by the exchange. But I think the larger issue is that of perception integrity: events such do not promote the perception of a safe place to invest.

In short, AT is not the enemy when it comes to this kind of fast volatility. We need to make sure that non-HFT’s don’t get wiped out as collateral damage because they seem to match an uninformed picture of “HFT”.

# Solutions Please?

The root of the problem is not the existence of HFT firms: they have merely adapted to the environment to maximise their profits. This is to be expected – in any other area we would describe this as “success”. The problem is the environment: a marketplace that rewards this behaviour in the first place. Fix the environment, and the marketplace will take care of HFT itself.

Price-time priority says that the “first in wins” when matching against others in the order book. It is where the advantage of speed is derived. This doctrine has outlived its usefulness, and it’s now time to re-balance the market rules since there is now a massive variation in the speed of traders. This is where I propose [[[blog:timematch-a-slower-order-book |TimeMatch]]]: an alternative set of market rules where every order is auctioned to the trader that is willing to give the best price. This way, technology works for the benefit of the marketplace – rather than against it. Without getting into a too much detail, retail traders would not notice anything other than they occasionally get price improvement on their orders. That is, they get a better price than they asked for – when their orders are caught up in fast price movements.

I feel this is a more natural solution to the issues surrounding the increased (now ridiculous) speed of trading technology – without harming all AT’s. I argue that the other proposals put forth in the public debate are ill-conceived knee-jerk reactions, without proper consideration of the unintended consequences:

* Cut the pipes: how would you decide who gets cut, considering HFT is all about gaming the system
* Transaction tax: would eliminate only a proportion of the predatory activity, at significant cost to the rest of the market
* Minimum resting times: this would help, not harm predatory HFT in Australia since they are liquidity takers.
* Randomised auctions: causes all participants to trade in the same fixed timeframes, set by the regulator. [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}) allows the market to set its own speed.
