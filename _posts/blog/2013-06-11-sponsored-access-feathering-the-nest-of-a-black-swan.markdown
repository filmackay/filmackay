---
layout: post
title: "Sponsored Access: feathering the nest of a Black Swan?"
date: 2013-06-11
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
# Market Access Mechanisms

Over time the equities marketplace has evolved from phone-based trade execution, to using computerised channels such as Direct Market Access.

## Direct Market Access

This is where a trader sends an order electronically to their broker who, assuming everything is OK, simply passes it straight through to the market. Unlike in the past, where the trader may have placed an order with the broker, granting them some discretion over when and how to execute it; DMA is simply a pipe giving you immediate access to the market. Think of it as a no-frills self-service offering.

## Naked Access

As latency (speed) became more of an issue in recent years, firms investigated ways to speed up their DMA access times. One of the central tenants of DMA is that the broker still performs checks on each order to ensure that the firm has the capital required to settle the orders, and that the orders do not create a disorderly market. Somewhere along the line DMA evolved into something more aggressive: naked access. This is where the broker effectively allowed the firm to send orders directly to the exchange, completely bypassing the broker. In this model the broker trusted the firm to “do the right thing” and not send orders for things they could not afford to settle, or create disorderly market. Now that’s real trust.

It has been reported in the US that 30% of turnover was conducted via naked access around 2010, with the SEC moving to ban the practice the following year.

## Sponsored Access

Regulators globally stepped in and questioned the validity of brokers outsourcing their responsibilities to trading firms in this manner. This delivered a new concept: sponsored access. The intention of this model is to be able to achieve the extreme speed permitted by naked access, whilst still ensuring the broker stays in control of their client’s trading. The problem with sponsored access is, that the manner in which a broker “stays in control” can be a little ambiguous.

Naked access has never been permitted in Australia, with a fairly strong regime of regulation around the checks that must be performed before electronic orders can flow through to the market. However, there is only a grey line between sponsored access and naked access.

A broker granting sponsored access to a trading firm would give them some software to run on their servers (or FPGA chip), so that when the firm’s algorithm decides to trade it calls this software to do a check as to whether the order is permitted according to the brokers’ requirements. If successful, the firm sends the order directly to the exchange. The broker never sees the order, only observing it in in the market just like everyone else. In the US there is a range of products which provide direct access to the firm, but perform risk checks in a hardware chip that is completely controlled by the broker. I don't see such products being pitched in Australia, leading me to believe that firms are being given software by their brokers to perform the risk checks. In this model (which I'd argue is exactly what firms were doing under naked access) there is a trust by the broker to the firm that they will do the right thing and make the necessary calls. Therein lies the moral hazard.

When you have a marketplace that rewards speed, as the electronic equity market does, and then you allow traders to have any kind of control over the risk checking of their orders – you have the ingredients for trouble. By definition the most profitable ultra-low latency trader is going to need the minimum possible risk checking, since every risk check costs time and therefore makes them more uncompetitive.

# Worst Case Scenario?

Many talk about the Knight Capital incident in the US in terms of it being a kind of "worst case scenario" reference point for algorithms run amok. I think it was far from it. Importantly, they did not lose more money than the capital base of their firm. In other words, while the shareholders lost a bundle, they did not need a bale-out. No third-party funds needed to be drawn to cover the losses.

During the malfunctions at Knight Capital, one thing other firms noticed that they were effectively buying massive amounts of liquidity – and paying away the bid/ask spread. The other firms started exploiting this fact (I mean, we all try to buy low and sell high, right?) and ramped up selling liquidity to them – and making near risk free profits. What if this had happened a lot faster, since it took a while for them to catch on that this was really happening? You can be sure next time there is a wounded trader in the market, they will be targeted - since they've seen this before. There is the potential that you could have massive losses (say trillions), inside a microscopic time period (say a few seconds).

If this were to happen you have a case where a firm has lost its capital base, and more - and who has trillions? The liability then goes to the broker, with as low as $10M in capital - that wont help much. Then it moves to the [National Guarantee Fund](http://www.asx.com.au/products/ngf.htm) with $100M. No stopping there either. Naturally many will take the view that this is "obviously" errant trading, and the trades should be busted. There would be a good case for this - but it would be a dangerous precedent since the trading would not in any way be "disorderly". Having someone (in error) buy massive liquidity from the market (buying at the ask and selling at the bid) does not in itself move prices - especially when a whole bunch of high speed peers are sitting there happily providing it and banking the spread. Whilst the root cause of Knight Capital's woes was [someone releasing the wrong software into production](http://www.nanex.net/aqck2/3525.html), the system needs to be robust ([antifragile?](http://en.wikipedia.org/wiki/Antifragile:_Things_That_Gain_from_Disorder)) enough to cope with these events.

There will be other causes to this kind of runaway event: for example it is quite possible that two ultra-high speed trading systems could interact with each-other in such a way that they behave in a completely unexpected way. This kind of bug could never be found in testing - since the algorithms would only ever "see" one another in the live market. Testing for every possible permutation of peer algorithm is, impossible.

The on-ramps for ultra-fast algorithms needs to be a lot more robust than it currently is, and ensure comprehensive risk checking is consistently performed - and in genuine real-time. That means the risk checks need to be ultra-low latency themselves, and certainly not performed on firm-controlled infrastructure. Put another way, making the trade-off between risk and speed needs to be done by someone who is not profiting from the speed and (as all firms/brokers are) passing the "tail risk" (read: really nasty unexpected events) to someone else.

# Is there a solution?

Yes there is. The problem in all this is that the party in the transaction that stands to make the profits from trading the quickest, is the one who in practice enforces the risk checks. This needs to change – and I don’t mean by making the broker do it. That too is a compromise, as brokers will market their services over the speed (read: less risk checks) in their trading interface. There is skewed motivation for a broker to do sophisticated counter-party risk validation on each order (required to prevent a runaway algo) because of the latency cost involved. That is to say if they did, they would be considered uncompetitive with other brokers who did not have this requirement.

The solution to all this is: do the risk checks at the exchange. This has the dual benefit of ensuring a level playing field of comprehensive risk checks (everyone gets the same checks and corresponding speed penalty), plus the exchange is in a position to assess the fact that the firm has not run out of capital in a run-away malfunction. The exchange can vett each order, ensuring that the order flow is consistent with the capital base of the firm, not allowing each order until that validation is performed.

I should note that some of the more basic vetting is done by ASX on futures, but these need to be widened and applied to equities as well. The vetting rules on futures are fairly basic, but they seem to be enough for ASIC to think allowing naked access to clients is OK since that routinely happens. I personally think this is an accident waiting to happen.

Of course, a natural hedge to the runaway algo effect is to [slow the market down]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}) and allow the market to set it's own pace – but that’s another story..
