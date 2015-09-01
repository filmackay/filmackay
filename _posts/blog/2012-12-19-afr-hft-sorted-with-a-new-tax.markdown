---
layout: post
title: "AFR: HFT sorted with a new tax?"
date: 2012-12-19
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
Keeping up the momentum, the AFR posted [this article](http://afr.com/p/business/financial_services/call_for_tax_to_rein_in_high_speed_yu9spgqBhufTGXnEXkDNEI) on "Call for tax to rein in high-speed trading". Unfortunately for the title, it's already in effect in Australia. This article is based on a pretty good report](http://www.fsc.org.au/downloads/uploaded/Changing%20Technology%20in%20Capital%20Markets_2182.pdf) from Baseline Capital.

> FSC chief executive John Brogden rejected any suggestion of an outright ban on high-speed trading of shares, but said regulators needed to keep a tight rein on the sector to prevent market manipulation and negative consequences for investors.
> “Both dark pools and high-frequency trading have a legitimate role to play in the market and as such we reject any calls for a moratorium or a ban on high-frequency trading in particular,” Mr Brogden said.

Well that is a step forward - a buy-side representative *not* calling for HFT to be put to the sword!

> However, the FSC warned that a small minority of high-speed trading – estimated at about 5 per cent – could be deemed as “toxic or harmful”. This included “front running” of fund managers, where traders see the orders of other investors and use their high-speed computers to place their own trades ahead of these.

The strategy being referred to here is not "front running" (which is the use of non-public client order information to prompt another trade). The (predatory) strategy being referred to here is where an HFT will take *public information* and work out what someone else is *probably* going to do. It is employed by many trading firms, just on different (larger) time scales. Why is it suddenly wrong when the hackers do it?

> There were also concerns about “quote stuffing”, where high-speed traders flood the market with a large number of orders for trades that are never executed, frustrating genuine investors.

There should be no concerns about quote stuffing in Australia. It has never existed, does not currently exist, and wont - due to the message tax already in place. What is there to be concerned about?

> “The activities that really concern us are the predatory type activities where people are trying to observe what is going on in terms of large orders and get ahead of those orders,” Schroder Investment Management Australia chief executive Greg Cooper said.

The problem with this is two fold: (a) you don't need to be a HFT to exploit this strategy, and (b) all sorts of traders have always exploited this possibility. As is currently the case there has always been a variety of traders all trying to second-guess what the guy "one up" from them in terms of time-scales is going to do next. HFT have just created a new category - doing it on even smaller time-scales. The fact that there's a new kid in town, shouldn't switch our mind from the fact that everyone tries to exploit this kind of strategy.

Just like every other type of trader that does not exploit private client information (ie. does not front-run), they can only do it based on public information - as that is all they have access to. There is, however, a need for the buy-side to *not be so predictable* in the way they trade on the markets - to generate the public signals for HFT to feed from.

The large brokers successfully campaigned to have broker ID's removed in 2005, I think there is a limit to what the market micro-structure should be doing for them. At this point I think the onus is on the buy-side to trade smarter, not try to use taxes to make up for their shortcomings.

> “That is the behaviour frankly that as a ‘buy-side’ person we are most actively trying to get away from. Certainly our view of the overseas experience is very negative. And people often look to the US more broadly in financial services as the country at the forefront of technology. In the high-frequency trading world, that is not a place we want to go.

Certainly there is situations overseas in the past where HFT's did front-run (eg. flash orders), but remember these were unintended consequences of reforms designed to protect buy-side. Careful what you wish for.

> Under the FSC’s proposal, high-speed traders that make excessive orders for traders – also known as “messages” – that are not executed would be penalised with a new tax.

This might be playing with terminology - but such a tax already exists, as it applies to all messages. If the whole point is to leverage greater penalty on those who send a lot of messages, and don't do a lot of trades - the current system does that. An HFT placing 10 orders and canceling them will pay a tax of 20 messages, whereas a buy-side placing an order that trades will pay for 1 message. That looks to me like a tax that penalises excessive un-executed orders.

The report then goes on to say:

> There isn’t really any true evidence we can find in Australia of genuine predatory high-frequency trading.

Ouch. This does seem inconsistent with the FSC's call for an additional tax, but in any case I'd argue I've got plenty of examples of predatory HFT. Having said that the scale of the activity is still very modest, and is very targeted at certain traders. Unfortunately for the FSC, it is their members that are the ones being targeted.

> “There are activities that can be identified that look potentially like quote stuffing behaviours, which occur in high frequency trading in the US.
> “But those things are not really noticed in Australia.”

I'd be interested in knowing more, but nothing I've seen comes close to genuine quote stuffing, since the message rates are nowhere near high enough. I find the ones who come closest are usually two (buy-side) algorithms fighting it out, not HFT's trying to obfuscate the market.

> Mr Brogden said any tax on orders should be levied only on those traders that put excessive “messages” through the market, so that it does not affect genuine investors.

The problem with this approach, is that message rates for genuine investors is increasing and will continue to as they employ more algorithmic trading techniques and seek to avoid adverse selection. While the market rules operate on the basis of "the first to respond gets to take the liquidity" - this will always be the case, and increasingly so. It is only a matter of time until real HFT strategies start to be employed by buy-side, just as self-defence against predatory HFT. Over taxing that can be detremental to on-HFT. And before you think: but what will they protect themselves against if the tax gets rid of HFT? Remember that predatory HFT does not require high message rates - it is just one signal that *some* of its strategies produce. And in Australia they currently don't.

Of course the alternative I propose for all this is to fix the market rules, then the whole argument around latency becomes moot: [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}).
