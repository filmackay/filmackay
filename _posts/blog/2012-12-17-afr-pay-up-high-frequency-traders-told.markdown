---
layout: post
title: "AFR: A little transparency would go a long way"
date: 2012-12-17
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
The [AFR](http://www.afr.com) ran an  [article on HFT](http://afr.com/p/business/financial_services/pay_up_high_frequency_traders_told_Ft8S4siOgG5MRCofN5S6BO), purporting to report on an increased desire to push more supervision costs onto HFT. The central tenant of the article does not make sense, and perhaps by extension the Treasury report it's based on.

> A substantial increase in algorithmic trading including HFT [high-frequency trading] – incorporating not only increased trading volume but increased cancelled orders and messages for each transaction executed – has led to a general increase in ASIC’s workload,

The terms are a bit muddled here - there are two items that ASIC charges the supervision levy. Messages: place, amend and cancel instructions; and Transactions: actual trades on the market. Since "messages" include cancellations, it really should read ".. but increased messages for each transaction executed"

> The current cost recovery model was designed in an environment where trades rather than orders were driving most of the staff costs for ASIC’s market supervision operational work,” the regulator says in its report.
> At that time, detecting and prosecuting market abuse caused by trades was ASIC’s highest priority, although some work did arise from orders – for instance disruptions caused by HFT.

The strange thing is the message-to-transaction ratio has actually *decreased* (as you'd expect) since the introduction of the supervision levy. I don't think it's a fair representation to say the market has become more onerous to supervise, more-so that you got the model wrong in the first place, and you need to adjust it. I'd just prefer people state the latter rather than invent reasons :)

Aside from the reasoning, I think this is a sensible observation. Personally I'd look to levy on Messages entirely. After all, 2 place Messages are still required (at minimum) to cause a Transaction. Removing the latter from the formula would still "capture" them.

After promoting the merits of increasing the levy costs on high "message-to-transaction" ratio traders, a loophole emerges in terms of market maker discounts:

> One option that could be considered would be to offer a reduction in the cost recovery levy, or perhaps even exempt continuous, two way market making activity from message based charges, subject to strict eligibility criteria and ongoing evaluation and measurement that the market maker is meeting its market making obligations.

HFT and market-making are very closely aligned - the former regularly representing themselves as the latter in order to gain cheaper market access from the exchanges. The obligations are not onerous, and there's little downside (other than a bit more market disclosure). This seems to go counter to the prior argument of the paper that *high order-to-trade ratio participants need to pay* more.

It would seem to me we have a difficulty here that needs to be addressed. ASIC and Treasury: how do you define HFT? The AFR article seems to keep up the inertia on this issue, in a blind-following-the-blind manner:

> High-frequency traders use sophisticated computer systems to trade large volumes of stocks in short spaces of time.
> They rarely hold their positions for more than a few seconds and often flood the market with large numbers of trade orders, or “messages”, that they never execute.

There is little "flooding" in Australia, precisely because of the cost recovery scheme in place (and the topic of the article). The above is an extract of a sensible statement on HFT *in the United States* but does not at all describe what is happening in Australia.

ASIC gives their view on what HFT is:

> HFT now accounts for 25 to 30 per cent of all lit market transactions and the high order-to-trade nature of HFT means it accounts for a substantially higher share of orders and messages than more traditional trading strategies do,

Personally I think this 25-30 percent figure is way over the top, but it all comes down to how you define HFT. It seems to me we are all spinning our wheels until we come to a definition on what HFT actually means. I think ASIC are including many forms of algorithmic trading (and not particularly fast forms) in this figure - and actually including the very people who have automated their trading in order to protect themselves *against* genuine HFT. It really does miss the point when you label them all "HFT" and place them in the one mental bucket with a note "to be charged more".

For the record, my definition of HFT has been styled in making the term fit the persona. Public opinion has already settled on "HFT" being the "guys with an advantage I can't match". Rather than trying to redefine public opinion, I define HFT as being the fastest form of algorithmic trading, the strategies that only work if you are the fastest. And by fastest, I mean the *very fastest* - the guys who actually win the race consistently - no matter how fast that is. Thes are the one with the advantage, the one everyone else is trying to protect themselves from, and the guys who sacrifices everything (intelligence, strategy and common-sense) for speed. By definition, 25-30% of the market cannot be the fastest.

The main difference between our definitions of HFT is: high message ratios. I don't think these are required for HFT, and can actually be a useful *countermeasure* to protect one's self from it. It is precisely the reason that Treasury has talked about providing discounts on the cost recovery to market makers - because fast and regular re-quoting helps you minimise bid-ask spreads in the face of adverse selection costs. I would purport the main reason many HFT commentators (and Treasury's paper) consider high quote-to-trade ratios as being a strong indicator of HFT is actually a misinterpretation. In the US, in order to be the fastest trader in the market, HFT firms have taken on the practice of "quote stuffing". This is where massive message rates of garbage (read: spam) orders are sent into the market in order to slow it down. This allows them to effectively "win" the speed race, by slowing down the competition. These high message rates do not define the activity however, they are just a  side-effect in the US market where the regulator does not seem too concerned about noise levels on the electronic markets - not the case in Australia. So if you are looking for high message rates in Australia, you won't find HFT - you'll find other strategies (like market making) that employ it, but in this case for a useful purpose.

(NOTE: Granted the above paragraph is very much an oversimplification of the real-world, and that "high message rates" for HFT are orders of magnitude higher than for any genuine market maker. But here lies the potential for unintended consequences)
