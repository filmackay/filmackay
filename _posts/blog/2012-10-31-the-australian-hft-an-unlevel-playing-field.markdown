---
layout: post
title: "The Australian: HFT an unlevel playing field?"
date: 2012-10-31
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
[http://www.theaustralian.com.au/business/opinion/andrew-main Andrew Main] wrote [http://www.theaustralian.com.au/business/wealth/why-hft-is-exploiting-an-unlevel-playing-field/story-e6frgac6-1226505646823 a piece] in The Aus on HFT, interviewing [http://au.linkedin.com/pub/zachary-may/3/69a/299 Zac May] the author of the [http://www.industrysupernetwork.com/wp-content/uploads/2012/09/140912-ISN-submission-to-ASIC-re-draft-market-integrity-rules-and-guidance-on-automated-trading.pdf Industry Super Network ASIC consultation paper response] I [responded to]({% post_url blog/2012-09-18-industry-super-network-asic-consultatation-paper-184 %}) earlier. Zac May says:

> High Frequency Trading is the creation and then the exploitation of an unlevel playing field

HFT certainly didn't create the market we currently have. It is human intuition that said that the guy that matches the order first gets the trade (price-time priority). HFT's have just become the most efficient at adapting to the market that already existed. Maybe Zac is talking about quote stuffing (in the US - it doesn't happen here) where HFT's can slow everyone else down with noise to give themselves an advantage. Fair enough - but not relevant to this domestic debate?

HFT certainly uses it's strengths in the marketplace, just like any other market participant - including the people Zac May represents. They are managers of superannuation funds, who naturally use their strength of asset management scale to achieve other relative advantages. Things such as cheap brokerage, not able to be achieved by retail investors; but not something being hailed as an "unfair playing field".

To be clear, "exploitation" is an emotive term - but can be applied to HFT in the same sense it can be applied to anyone who trades for profit. The fact someone exploits an opportunity is hardly a big deal - assuming it is not fraudulent or illegal. The real query comes on the "unlevel playing field". What particular type of unfairness is he talking about here?

> Some people are paying ASX to allow them to be as close as possible to where the bread drops, [...]

The direct way to correct this issue would be to refuse to provide market data in any way other than one: the fastest. The ASX would rip out a whole lot of older/slower technology, and say: the only way to get ASX data and trade is to be co-located at the ALC with an ITCH feed.

I can hear the outcry. Brokers (the suppliers to Zac May) would be up in arms that they are forced to change their technology and use super-fast feeds //that they do not want//. No doubt the costs would be passed through to the people Zac May represents. The reason they wouldn't want it, is that they know that the additional speed will not help them. They know that nothing will improve for them in the extra millisecond they gain, since they just don't have the capability to do anything with it.

How is it then, that the ASX is being unfair by providing a variety of services at different price points, using different technology for the customers to choose? The real issue is not that the ASX provide a variety of access mechanisms, but that some customers can move faster than others. Hardly ASX's fault?

> You have to ask yourself why ASX provides privileged access to information for some participants. It's not just so they can get the information fast, it's so they can get it ahead of other people.

Exactly what privileged information does the ASX provide to some participants? None. They get the information ahead of other people because they can be bothered going to the pond to get the bread.

Besides, I would say the whole point of getting information fast, is so you can get it ahead of other people?

> And that causes other investors to start asking themselves: 'What do they know that I don't?'"

Other investors need to acknowledge that there is a lot that HFT traders know that they don't. Remember HFT's only congregate in the pond to beat each-other: not other investors. They already have the other investors beaten who are waiting for the bread to be delivered to them via courier.

The issue is not that HFT's get a sneak peak at information, it is the arms race that is taking place in the pond. It creates a very fragile market, and one that is prone to chaos - as clusters of fast and stupid algorithms get up to mischief. All this in the knowledge that the ASX will have to bust the trades if things get really out of hand.

> But, he said, it should be possible for regulators to eliminate that advantage. Some jurisdictions had introduced a half-second delay on orders, others were proposing random delays, and there was also talk of "sealed bid double auctions" at random intervals to remove the time advantage for HFTs.

* Half-second resting times: would help predatory HFT in Australia, since they are liquidity takers not makers.
* Random delays: predatory HFT can work around this, it does not eliminate their processing advantage.
* Sealed bid double auctions: means regulators need to "pick winners" by choosing the interval size used, creating a lot of inefficiency for algorithmic trading in more than one market. (that is, the kind of algorithmic trading that Zac May's members use)

One solution that means avoids all the above pitfalls, let the market decide how fast it wants to operate: [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}). That way you don't force the genuine HFT liquidity providers to slow down (extra risk, wider spreads, more cost to Zac's members), you just allow everyone to trade at their own individual pace.

> Also in Australia, a small ASIC levy on all orders, not just executed orders, hits the economics of HFT where only about one order in eight is actually executed.

This is already in place - it came in at the beginning of 2012.

> Greg Yanco, head of markets at the Australia Securities and Investments Commission, copped criticism for calling for calm over the whole HFT debate but says he doesn't want to call for legislation against the few that might disadvantage the many.

Bravo! Greg continues:

> "People see trades going through at best bid or offer, what's called the priority price," Mr Yanco said, "and assume they are HFT when they are actually dark pool crossings." He said that would cease to happen with the probable introduction next year of the Meaningful Price Improvement rule, under which you can only do smaller trades in dark pools at prices that are better than those available in the "lit" market.

Be careful of unintended consequences here. By bringing a rule like this in, you've now got a real concept of a NBBO (national best bid/offer price). Is this NBBO centrally aggregated? Where? By whom? How precise does the measurement of time need to be? How long after the NBBO changes, do you have to report a unimproved dark trade? The speed of light may seem fast but it's not infinite. This could be one step down the US road..

> Others include having a mandatory "kill switch" in the offices of market participants doing algorithmic trading of any sort, including HFT.

I don't think this style of kill switch will achieve anything. Any algorithmic trader with any sense will already have one (for self preservation). It's their competence that's in question here - would you trust Knight Capital (and it's competitors) to build their kill switch properly? Kill switches need to be where you can trust them: at the exchange.
