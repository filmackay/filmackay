---
layout: post
title: "HFT Market Reforms"
date: 2012-09-29
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
In reviewing a number of the recent articles, I've outlined some proposed solutions to some problems created by ultra-high-speed HFT. Here is a summary of them all in one place. Unfortunately we cannot solve all problems at once - the ones I am trying to address here are:

* High speed latency arbitrage on Australian equities: where HFT's use their speed to move ahead of others when the market movement is clear. This delivers a liquidity-taking strategy for the HFT, with higher probabilities of adverse selection for other traders.
* Algorithms that 'sniff out' the ASX CentrePoint orders, and other algorithms, by placing lots of small orders (quote often for 1 share) whose prices cross the bid/ask spread. This allows them to tell what side of the market those in the CentrePoint "dark pool" are sitting on, giving them extra intelligence on what other traders are trying to execute.

The solutions have a simple theme: *execution venues should allow liquidity providers to have more control over their orders*. In this vein, the exchanges would implement:

* Micro auctions
* Minimum execution sizes
* Exchange-side algorithms
* Visibility control

# Micro Auctions

The execution venues would use a [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %})-based order book (instead of the current price-time priority), allowing the liquidity provider to choose the time-frame over which a short auction auction will operate every time a trade is matched.

# Minimum Execution Sizes

This allows the liquidity provider can specify the minimum size that each parcel of their order can execute in. eg. this would prevent 1-share orders from executing against them. Whilst this is beneficial to retail traders who then get stuck with a (expensive) single share, it also prevents algorithms from gaining insight into what others are doing.

Note that this allows 'all-or-nothing' orders, by specifying the minimum execution size as the size of the entire order.

# Exchange-Side Algorithms

A lot of the asymmetry in algorithmic tools lies in the fact that achieving low latency is an capital intensive exercise. Constant refinement, upgrades and improvements are required to keep an algorithm running at top speed - since all your competitors are constantly improving as well. There is always a select few in the market that have the best, at any given time, implementation of a particular type of algorithm. By 'best' I guess I am really saying, fastest - so we are assuming these algorithms are fairly simple and stupid beasts - and largely compete on their speed. Note that this competition does not benefit anyone (but themselves), so there is no commensurate improvement in market quality as a result of this battle.

# Visibility Control

Allow lit and dark liquidity to co-exist, don't banish the dark stuff to the dark pools! This is very controversial, and I need to do some more writing on it - however the liquidity provider is king. If he doesn't get what he wants, he goes somewhere else (read: fragmentation). He can get darkness somewhere, just at further cost to the market, so give it to him in the central market. More on this later..

One way to 'level this playing field' is to provide a perfect (from a speed point of view) implementation to everyone, on an equal access basis. This can be achieved by implementing algorithms within the exchange, and allowing trading firms to place these order types - which then get run within the exchange computers. This is *not*, and does not require co-location by the firm. It is simply a matter of a firm, instead of specifying a simple limit or market order, sending an algorithmic order. The exchange's computer then runs the algorithm, creating whatever limit and/or market orders result from the particular strategy.

This capability would have three key impacts:

* Everyone now has equal access to that particular algorithm. All firms can operate at 'zero latency' - and no-one can out-run another. High speed traders no longer have the ability to withdraw orders before hit by these algorithms, since they are running at zero latency.
* Every existing HFT firm's implementation of that algorithm instantly becomes worthless. Since no HFT firm's algorithm can ever compete with an exchange-based algorithm in speed terms, no-one would ever want to use the external algorithm again.
* Competition between ASX and Chi-X would flourish from a focus on "sticker price" fees, to diversity and innovation. Exchanges would compete on new algorithm types to assist firms - of all types.

The sorts of basic algorithms that could be useful:

* Sniper: liquidity taker over a particular price/volume hurdle
* Iceberg: OK this one has been around a while, but a few more controls are needed
* Pegged: attach the limit price of an order to some other market variable (bid/ask)
* Stop: order that is triggered on a price level being breached; trailing varieties
* One-Cancels-Other
* Bracket
* Good After Time: allows the liquidity provider to specify a time when the order should become active. Assists in timing orders on multiple venues precisely, so as to prevent predatory strategies.

Of course all these algorithms would need to come with a suite of features to prevent themselves from being 'sniffed out' by other algorithms, since the capabilities of these algorithms would be widely known. Things such as: time/volume randomisations and thresholds would allow them to avoid detection - by ensuring they behave slightly differently in every instance. All algorithms would be dark - obviously you don't want information being leaked on stop orders, or what underlying strategies are being used during execution.

Extra effort would be needed (over and above what exchanges usually provide) to also make these algorithms very safe. Given that these will never need to compete on speed (operating within the exchange's computers), it makes it a very good environment to implement a lot of intelligence to prevent the kind of non-linearity that currently causes massive nonsensical spikes in the market.

## Custom Algos?

Would it be totally crazy to suggest the idea of firms being able to create their own algorithms, to run on the exchange's servers? Now, there are many areas of concern here, but stick with me!

One impact this would have (if implemented correctly) would be full diversity of algorithmic activity, ensuring you have a good spread of behaviour in the market - which leads to lower volatility. This would allow equal-access to algorithmic tools to all participants, meaning no technology war in order to be the fastest. Every firm would now be 'the fastest' and would now compete on the *intelligence* of algorithms rather than the outright speed. Speed is dangerous because it leads to poor and fragile behaviour - as safety and good strategy costs in performance.

For those worrying about algos seriously screwing with the markets in this scenario, well what can I say but that's a valid concern! But it may be possible to manage the risks. The algorithms would obviously be heavily 'sand boxed' and be prevented from impacting on the performance of the exchange itself beyond reasonable limits. I don't think it's impossible, though, to implement this in a workable fashion: but your quality control on this would be extremely high. The up-side is that because it's fully visible to the exchange you actually have the ability to control the process, rather than trust all the "Knight Capital"-esq firms: that they can do their software deployments correctly.

[to be continued..]
