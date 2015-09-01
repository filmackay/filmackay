---
layout: post
title: "TimeMatch: a slower order book?"
date: 2012-09-04
author: Fil
categories:
- blog
- hft
- TimeMatch
img: hft-chart.gif
thumb: hft-chart.gif
---

TimeMatch<sup>no-TM</sup> is my current thought experiment on designing a modern public order book. Flowing on from my previous posts, it contains special features to discourage uninformed investors from fragmenting the liquidity of the market via disparate venues in the hope of achieving better prices. The idea behind TimeMatch is that we improve the public order book to the point that uninformed investors experience no speed/technology disadvantage, but continue to benefit from the larger liquidity pool.

You could think of TimeMatch is a public order-book alternative to NYSE's [retail liquidity program](http://exchanges.nyx.com/node/3840).

### Why does it work like this again?

One of the relatively unquestioned aspects of order book design is [price-time priority](http://en.wikipedia.org/wiki/Central_limit_order_book). It says that you should get priority of execution if you post the best price. If the price is equal to someone else's - then it goes to the one who was first. If you think in terms of human processes, this intuitively seems fair. Give me the best price available, but give it to the guy that's been in the queue for the longest amount of time. No queue-jumpers please?

Over time the dynamics of the market have changed fundamentally with speed of technology. We now operate in a market where the speed of the market is at least in part working against the interests of uninformed traders.

### What's your beef with Usain Bolt?

For uninformed investors, execution speeds of a split-second are undoubtedly better than that of several seconds - we can work more efficiently and have a shorter period of uncertainty particularly when working with several orders at once. I would argue, however, there is no benefit to the uninformed investor if their order is executed in a few microseconds, as opposed to 1 millisecond. (it probably takes your LCD screen ~7 milliseconds to update, so no - you won't notice :)

When response times get very low, a technology race emerges and the benefit of an ever-faster market platform shifts to the trader that can move the fastest. When trading against an uninformed order, the high-speed algorithms all race to trade against it first. This means your order was awarded to the firm that was able to move the fastest, getting you only a benefit of faster execution - not a better price.

So yes, speed is good - but it's not everything. At some point I don't value it at all. I have no problem with Usain Bolt being faster than me, but I just choose not to race him!

### Controlling speed

So how then do we meet the needs of a variety of traders in a single venue, given that some prefer speed over all else (HFT) and others would prefer a better price (buy-side/retail)? Instead of complex and inefficient schemes such as mandating minimum order resting times, slow moving markets or imposing targeted HFT taxes - how about we let investors decide?

An investor should decide, when submitting an order, the time period over which the execution (or auctioning) of the order will take place. This could be thought of as "price-time-time priority". Orders would only be able to match against one another if the time period (supplied by the buyer and seller) *and* the price are overlapping.

Once a match has taken place, an auction would be conducted for the time period specified. This would allow any other trader to out-bid the liquidity taker, in supplying price improvement to the liquidity creator. Thus the liquidity creator has the potential of price improvement from other bidders who may arrive at the market after the initial bidder.

This market-based solution allows for the participants themselves to decide how quickly they want their orders to be executed. A scheme such as this has the potential to address the issues of [adverse selection](http://en.wikipedia.org/wiki/Adverse_selection) and latency arbitrage where faster traders monetise their speed advantage from the market.

### What would happen?

The effect of this kind of order book would be that each trader in the market would analyse what their execution timeframe is. HFT firms would choose "time 0" for instant execution of their orders (no auction), while a human trader may chose to run a 200 millisecond auction for "fast enough" execution with the potential for price improvement amongst the algos.

You would then see a reversing of the trend that occurred in development of high speed matching venues. Instead of uninformed investors 'cheap' orders being disproportionally picked up by HFT, they would go back to matching more naturally against other uninformed investors. This is exactly what off-market trading mechanisms such as broker crossings, and dark pools try to achieve, but creating a lot of other question marks at the same time. This would result in improved prices for both uninformed sides, with no cost. Of course HFT would still be allowed to compete on the same basis as humans, but their speed would not be able to be used to obtain access to the cheap orders of those who don't value it.

The best thing about this method is that the market regulates it's own speed. If the market decides it wants to keep trading 'instantly' with no auction - then all traders will send their orders with "time 0". I think once the buy-side do their trade cost analysis, they will quickly find the answer as to whether this is of benefit to them.

This would help achieve my stated aim of building better liquidity - helping prevent the departure of the most uninformed orders to fragmented venues.

Next we look at some [practical examples]({% post_url blog/2012-09-05-timematch-examples %}).
