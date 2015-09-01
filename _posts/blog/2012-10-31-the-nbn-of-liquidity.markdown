---
layout: post
title: "The NBN of Liquidity"
date: 2012-10-31
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
Previously I have proposed [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}), a system where every order is auctioned in a timeframe that the order's owner chooses. This would mitigate the speed advantages enjoyed by the technology firms. It basically means that investors get to choose, when they place an order, how much they value speed of execution verses improved prices. They are not forced to value speed of execution over improved prices, as the current price-time priority rules say. Let's look at another thought experiment: a market modeled on the NBN.

# National Broadband Network


To those not in Australia, the [NBN](http://www.nbnco.com.au/) is a new government owned monopoly provider of data services. It will give 90%+ of households fibre, and the rest a mix of fixed wireless and satellite delivery. NBN is wholesale only, so preserves the appearance of competition via value added retailers. It is in the early days of construction, but some towns are already live and operating.

(Just for the record, while I would love to get the NBN (like most, I'm not in the 3 year horizon), I'm not all that happy about the amount of money being spent on it. I think there should be a customer contribution to connectivity, rather than it being "free". I like the way they have done the [network extension program](http://www.nbnco.com.au/getting-connected/network-extension.html), and wish the whole network could be built that way! There should have been some acknowledgement that the NBN really baled out Telstra from the consequences of its crumbling copper network which needed to be replaced. I would have connected the early adopters, but kept the late adopters on copper for a while yet.)

The NBN encapsulates the idea of: do it once, and do it properly. It was devised to avoid the situation where a network builder naturally wants to extract the maximum price from consumers, but the ability for them to slash the price acts as deterrent for anyone else to overbuild and provide direct competition.

# National Liquidity Network?


Lets think of the equivalent in electronic markets: the NLN. The central problem it could solve is: liquidity fragmentation. By spreading out the liquidity in multiple liquidity venues, you pay higher prices since you need to try harder to get (and often can't get) the best price. Of course technology helps fill this gap (smart order routers), but they often create predictability that predatory HFT firms prey on. It comes with cost.

What this thought experiment is about is the formation of a government-run matching engine, but not an exchange. Instead of private operators all (ASX, Chi-X, Liquidnet etc.) all running their own matching engines, they would use one: the NLN.

Sounds crazy? Probably, but so did the NBN. Never thought that would see the light of day!

The NLN would be:

* a single national central order book
* open to all liquidity types: lit and dark
* the publisher of consolidated market data
* funded in the same way as the supervision levy, not for profit
* open access

To facilitate this, liquidity would need to be mandated to go though the NLN (much like in the same way telcos were pushed at gunpoint to deal with the NBN). Broker crossings would be eliminated, and dark pools unable to run their own matching technology. Gone is the need to mandate meaningful price improvement, since in this system a trader can't miss out on a better price. The published NBBO (national best bid & offer) prices would be real - unlike the US where they are for "display purposes only".

# Exchanges or Brokers?


It's always been an issue in the industry: when will the ASX bypass the brokers (or vice versa)? At this point I think there is a valid need for the two to remain, since you are only outsourcing the most commoditised aspect of exchanges to the NLN: running a computerised matching engine. Having said that, it is a fact of life that we all need to re-evaluate our contribution to the value chain. Ask Sony, Kodak or Microsoft.

## Exchanges


Lets imagine you can only place orders on the NLN with a markets license. Market operators also have the ability to add value (like Telstra on the NBN) and differentiate themselves though:

* enhanced order types
* higher level execution tools
* trade distribution networks
* discovery of dark liquidity
* cost

OK, the ASX would feel it has a lot to lose. But will Telstra actually (despite their initial reactions) end up a stronger organisation post-NBN?

## Brokers


Brokers would no-longer be required to connect to more than one market operator. They would only do so to access the value-add services that they provide. As far as liquidity access is concerned, every market operator now has access to all the liquidity. Hello competition. Now trading via a "dark pool" will now be as safe, as you can't get dudded on price!

# Market Reform


Of course the matching engine would be quite different to the ones we have in operation today. Instead of just accepting vanilla orders to buy or sell, market operators would contribute software algorithms - and run those algorithms on the NLN. This would allow innovation, without the latency arms race - since these algorithms would in effect be running at "zero latency". Now everyone has equal access, and everyone is a HFT.

Naturally proposals such as [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}) are still relevant in this imaginary world - that would be just one type of smart order that the market operators could design and provide to their broker clients.

## CLOB by Another Name?


The concept of a CLOB (Central Limit Order Book) has been [discussed for many years](http://books.google.com.au/books?id=9ihjAj9eztAC&pg=PA67&lpg=PA67&dq=clob+reg+nms&source=bl&ots=DE2iUTg6a6&sig=CdnsIUb1PaEBsIzIahbQ9EovNMM&hl=en&sa=X&ei=m6KZUK-QLaafiAemn4H4Cg&ved=0CDYQ6AEwBA#v=onepage&q&f=false) in the US, and is essentially the same idea as the NLN. Unfortunately the US opted for [Reg NMS](http://en.wikipedia.org/wiki/Regulation_NMS) and the rest is, well, history..

## Simpler Reform


It's quite interesting to look at the regulations in play or on the table that would be unnecessary under a NLN scenario:

* NBBO reporting restrictions
* Minimum price improvement
* Maker/taker rebates
* Best execution connectivity obligations

## Simpler Trading


There is also a whole host of issues that are increasingly costly for market participants that would dissapear:

* Cross-venue arbitrage
* Fragmentation costs (where liquidity providers are enticed to a dark pool you have no access to)
* Time synchronisation
* Infrastructure fragmentation
* Queue jumping by circumventing liquid venues
