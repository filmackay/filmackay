---
layout: post
title: "Industry Super Network: ASIC Consultation Paper 184"
date: 2012-09-18
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
A friend sent me a link to the [Industy Super Network's response to ASIC's Consultation Paper No. 184: Australian market structure: Draft market integrity rules and guidance on automated trading](http://www.industrysupernetwork.com/wp-content/uploads/2012/09/140912-ISN-submission-to-ASIC-re-draft-market-integrity-rules-and-guidance-on-automated-trading.pdf). Long title, but not a bad document. Here's my thoughts:

> ASIC’s attention to High Frequency Trading (HFT), in particular, is appreciated.  As discussed in more detail in our comments below, we encourage ASIC to carefully explore the potentially significant risks that HFT presents to market fairness and allocative efficiency, in addition to ASIC’s current emphasis on market integrity risks.  A thorough and public assessment of these issues would be an important part of restoring  confidence in the lit markets, which has been undermined by HFT.

There's a few points of confusion here. Firstly, it is almost assumed in this paper that HFT is bad for the market. I think it side-steps a few questions:

* How fast do you need to be to be considered HFT?
* What types of strategies are considered HFT?

Now the paper does state some kind of definition:

> HFT is, in our view, a subcategory of automated trading whose strategies rely on the capability to obtain and respond to market information at high speed with low latency.  Typically, for these strategies to be successful, they must not only be fast, but they must obtain, process and react at higher speeds and with less latency than other market participants.

No arguments there, but how fast is fast?

My definition of HFT is currently (and yes it is a moving target): firms with a tick-to-trade (ie. being able to respond to market actions) of single digit microseconds (ie. less than 10µs). This means you are a specialist HFT firm, at the forefront of the speed race, and your strategies are pretty simple/stupid as they are no doubt implemented on FPGA technology. The many firms in the 3-digit microseconds latency (ie. 100µs+) I would argue are quick in human terms, but not HFT. Lots of prop trading and market making firms operate in this timeframe, and have very sophisticated automated strategies operating on servers running Linux.

To summarise my view of these questions on HFT:

* Speed: 10 microseconds
* Strategy: pretty stupid (you can't do anything too smart under 10 microseconds)

Under these definitions, I would agree that HFT is generally bad for the market. By "bad" I mean it extracts a cost from the market, without providing a corresponding benefit (eg. liquidity). Predatory HFT is characterised by parties forcing themselves in-between two natural traders that would have otherwise traded, and extracting a 1c spread in the process.

I am all for traders protecting themselves (or being protected) against predatory HFT, but that is based on limited scope of HFT above. I would not want regulation to curtail what I consider to be the legitimate non-HFT activity of market makers and prop firms, using strategies which provide valuable liquidity. eg. Optiver, SIG, Tibra etal.

> (i) Market integrity: HFT, particularly under stressed market conditions, can erode liquidity and contribute to a breakdown in orderly markets. The capacity of high frequency traders to flood the market with orders magnifies the risks to market integrity arising from automated trading in general.

Whilst I can understand the authors were thinking of specific instances of HFT activity, I think it misses the mark in terms of characterising the dangers of HFT.

HFT certainly does erode liquidity, but it doesn't do it under stressed market conditions. It does it all day, every day. Not only does it provide a disincentive for others to provide liquidity (via the threat of adverse selection), but also creates the appearance of liquidity that disappears when it is needed. Since they can move so fast they are able to provide what some people call "false orders" - that is, real orders that they can remove before anybody is able to trade against them. Maybe "shadow orders" would be more accurate? Thinking of HFT in stressed market conditions has been very popular since the flash crash: because you noticed it. What you don't notice is the constant drone of strategies being employed when the market is ticking along with no headline grabbing crashes.

HFT can contribute to a breakdown in orderly markets, but they certainly don't have a monopoly on that. One area that HFT excels in causing chaos is feedback loops - clusters of very fast algorithms start reacting to one-another, and being programmed the same way with a very stupid strategy (because they need to be so fast), can cause a quick spike or dip in prices. Several occurrences a day in the US is not uncommon, and they are starting to take hold in Australia.

The US equities market has shown how HFT can 'flood the market with orders', but this approach has yet to take off in Australia. My view is that that due to the [message tax](http://www.asic.gov.au/asic/ASIC.NSF/byHeadline/Market%20supervision%20and%20competition%20cost%20recovery%20FAQs), predatory HFT in Australia will be a liquidity taker, not a liquidity (noise) creator. As such the whole notion of HFT's creating a flood of orders I think is a misunderstanding of the Australian market. Targeting regulatory action at such a non-problem will be of no benefit.

> (ii) Fairness: Structural advantages (largely derived through technology) can unfairly redistribute profits from traditional long term investors to HFT traders. Many HFT offers to buy and sell are not bona fide and their objective can be to confuse other investors.

As long term investors, super funds are actually less exposed to HFT, as the exposure is proportional to the portfolio turnover. The consummate "day trader" is the one most exposed.

Whilst technically buy and sell orders on an exchange are always bone fide, the above interpretation is understandable given that if the fastest firms in the market have the ability to quote with little risk of being matched. These firm can withdraw orders should there be any mood shift in the market (eg. the orders ahead of them in the queue start to get executed). In this situation, these firms are able to withdraw their liquidity exactly at the time it would normally benefit the market. As such these orders can be thought of as like 'shadows' - constantly moving beyond your reach. This kind of liquidity is just an illusion as it cannot benefit you - disappearing just as you go to grab it!

While the technology-poor participant will argue: 'advantages derived through technology are unfair', are you really suggesting that advantages of all kinds should be removed? If so, why not regulate that brokerage is the same for retail as buy-side: that is an advantage. At the end of the day the marketplace is has a mix of participants with different advantages - that is not a bad thing in itself. We should look at the market rules before trying to consider some lowest-common-denominator approach to ensure that the fastest firms get slowed down. The free market can resolve these problems, it just needs the ability to innovate. Dark pools are an attempt to provide trading platforms more amenable to non-HFT, but I think the more regulated (lit) markets are yet to show their potential for innovation.

> (iii) Efficiency: HFT, insofar as it is chartist trading, would appear to risk undermining the efficiency of the market, particularly their capacity to facilitate the allocation of society’s scarce resources at low social costs.

Not sure what's going on there, but in my experience human traders are chartists; and HFT focus more on sub-tick opportunities.

> ISN recommends that ASIC impose a moratorium on HFT at the exchange level requiring orders that are received to be maintained until exposed to matching,

What is meant by this - how would you define HFT for the purposes of this short-term shutdown? I'm assuming that your definition of HFT is not as tight as mine, meaning all market makers would be offline..?

What you are advocating here is elimination of amend and cancellation instructions, so a placed order stays until someone matches it. This would actually create a disincentive to create liquidity, giving the HFT firms a leg up since they would have a captive market of targets that cannot withdraw their orders.

> which matching would occur in pulses separated by meaningful periods of time.

This would have the effect of slowing the market down - in principle a good idea, however I prefer to allow the market to control the speed rather than exchanges to lock everyone onto the same speed. This idea is explored in [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}).

> This would be combined with complimentary rules against internalisation prior to such pulsing and the opportunity for potentially better prices.

Ah.. attacking the self-interest of broker crossings, and the foundation of dark pools; yes the brokers have held onto this one (against their collective interest I feel) since the market begain. Yes I agree that broker crossings are 'queue jumpers'; but not sure if it is possible to *force* a broker to always join the public queue on each occasion? A fine-tuning reform for another day perhaps.

> The moratorium would allow technological and market developments to proceed only after the risks have been carefully studied by ASIC.  Further, the benefits of technology could be brought to bear for all investors in the public interest, not just a small subset of traders.

Personally I think it is too late to de-automate the market. Perhaps the cleanest way to do it would be to bring the chalkies back, but then again they weren't perfect either (being tall and loud on the exchange floor had advantages)! Almost everyone is now using execution algorithms, and it's a very slippery slope between there and HFT. Having regulators choose arbitrary measures like quote-to-trade ratios, or randomised response times and the like is very dangerous. We are better off fixing the rules that created the game play in the first place; it is possible but we need to question some of the fundamentals.

Having technological progress limited by ASIC's study would be problematic to say the least, why not just allow the market participants to defend themselves - then you have a more adaptive response as the market inevitably evolves.

The problem with predatory HFT is that it only benefits themselves, there is no commensurate benefit (of competition) to the other participants in the market. Once we fix this anomaly, the technology effect will flip - and become a benefit, not a threat.

> HFT firms' often rely on, and pay for, certain structural advantages:
Co-location.  By paying fees to the market centre or exchange, an HFT firm can receive a
privileged location for the HFT firm’s trading computers, which allows the computers to receive
data from the market centre more quickly, and send responses back more quickly.

In Australia, co-location is available to everyone on an equal access basis. Costs are fairly reasonable (sub $10k/month at the ALC). If I were building any trading business, I would be asking why not position all infrastructure at the ALC/Equinix, regardless of latency. Co-location at these centres is certainly not a ultra-premium service only affordable by a few.

> Customised and time-advantaged data feeds received directly from the exchange or market
centre.  For a fee, HFT firms can receive market data faster than the public tape and the data
might include information that is not included on the public tape.

In Australia these are available to everyone, and there is no special feeds available just to HFT firms with extra data than on the public tape. Contrary to much of the media reporting there are no flash orders or similar in Australia (on the lit markets at least, who could say about the dark pools?). Both exchanges use ITCH which is actually technically incapable of customising the feed to specific recipients (as a result of the fact it is so optimised for performance).

While there are a bunch of delivery technologies (ITCH, FIX, OM API, ITC) - they have different performance and usability characteristics. One is not designed to provide a faster feed at a higher price point. When considering the 'advantage' of having a technology that is 1 millisecond faster, you need to ask: what would you do with that millisecond?

Having a standard broking firm co-located at the ALC with that extra millisecond will mean: nothing. They do not have the technology or business model in place to make the most of it. We therefore shouldn't be singling out cases where there is faster technology, and say that that is a case of exchanges playing favourites to HFT firms.

> Access to special telecommunications infrastructure.  An example from the US: to facilitate
trading strategies across securities markets (located in New York) and commodity derivatives 3
markets (located in Chicago), boutique telecom companies have laid special fibre optic cable that
is more direct than the pre-existing cable between these cities (saving about 1.4 milliseconds in
message travel time versus the original cable) and a microwave beam system (saving perhaps 4.5
milliseconds versus the original cable), with another microwave beam system under construction
(saving perhaps 6 milliseconds versus the original cable).

Yeah, this stuff is pretty insane (and profitable - under the current market micro-structure). I'm not aware of any microwave links Equinix-ALC but I guess someone is at the very least looking at it.

While this is all pretty disconcerting from a competitive standpoint, just remember that these types of speed enhancements aren't really a concern for you. People using these kinds of telecommunications services are already faster than you, they are jumping onto even more insane services only to beat other HFT firms. If these really expensive, exclusive services did not exist - they would only be giving up profits to someone else in the speed club - you're unfortunately not a member.

> For some HFT firms, affiliation with trading systems operated within the same corporate group
(such as internalised trading platforms, including dark pools).

This is a major issue. I think it is fair to make dark pool operators get a license (a new kind - something more than an AFSL!); that provides oversight in the myriad of moral hazards that they face. I think the following obligations should be considered:

- Requirements of disclosure of trading and disclosure rules
- Auditing of reality v disclosed rules
- Timeliness obligations (immediate trade reporting)
- Market data obligations (after-the-fact; T+0, T+3?)

Whether dark pools should get a markets license, or a new type of license depends on who you work for. My view is that they should at least be better than an AFSL.

> Some markets will provide participants, for a fee, with a “flash” of an order before routing it to
another market for execution. [...]
ASX has publicly confirmed it does not issue “flash orders” [...]
Whether Chi-X issues flash orders is not readily disclosed to the public [...]

It is impossible for the ASX to have ever offered flash orders without it being widely known. However, the absence of flash orders is more to do with regulated order routing obligations (or lack thereof) than whether exchanges want to help HFT firms.

Similarly, Chi-X Australia certainly do not employ flash orders. I am sure they would verify this fact if asked.

> We have been advised, but have  not independently verified, that most Australian dark pools do not permit flash orders and in fact prohibit participation in the pool by high frequency traders (or offer an option for investors to prevent their order from interacting with HFT)

Yes talking to dark pool and HFT firms is a little like dealing with MI-5, you wont get much confirmation from them even about the obvious, because they are actors in a war. Depending on how strict your definition of 'flash order' is, one might be able to argue that polling an internal order book (or dark pool) could be similar to an 'internal flash order'? That's about as close an association as I could make based on my knowledge.

Yes dark pools are generally designed for non-HFT firms so they let you specify all sorts of execution limits like who you do (and don't) want to trade with. However as their name suggests, they are not as transparent and don't have the same obligations to their clients (at this point) as the markets operators have.

> [...] regulators [...] have allowed a stratification of market data dissemination and trading messages to occur.  Regulators have already determined that selective disclosure is unlawful -- if a listed company proposed to sell its annual report to a select group of hedge funds a day before public release so that those funds could trade on the information to the disadvantage of long-term investors, this would be enjoined and punished.  This is true even though market prices would presumably move closer to fundamental value sooner as a result of the trading.  Put another way, the regulatory interest in market fairness and rewarding judgement and analysis in investing outweighed potential efficiency gains arising from unfair structural advantages.  The evolution of disclosure obligations in respect of market information has been allowed to evolve outside of the view of fundamental investors, without significant buy side consultation and participation, and an unlevel playing field has come about.  We believe this difference between disclosure of fundamental information by listed companies and market information by exchanges should be carefully considered, studied in light of first principles of securities regulation, and remedied as
appropriate

I guess what you are saying here is: treat market data (prices) the same way that you company announcements. The suspension of a stock during a price sensitive announcement would be analogous to the gaps in-between the 'pulses' of the market. There are then large swathes of time for everyone to become equally informed.

I can see what is being said: but I feel it is a little lazy for the buy-side to complain at this late stage of the technological advance of electronic trading. Firstly, I think the buy-side should have invested prior to this in technology (or at least funded the sell-side to), to counter-balance the situation. The buy-side have enjoyed a massive reduction in market access (ie. brokerage) as they have screwed the sell-side down and down. What the sell-side have done is sell the same simple execution services, in a reverse auction, while all the time having it cost the buy-side more through adverse execution. What should of happened is that execution services brokerage did not plummet to it's "almost zero" level - but the product kept up with the technology race.

In terms of an unfair playing field being created due to market data stratification, I would simply return to my previous point: no-one gets a really fast data feed unless you can actually do something with it. There is no point the buy-side getting the best data feed possible, if they don't have the right tools to go behind it. It is not the exchange providing different products (as long as on an equal access basis) that causes stratification, but the business models of the firms themselves. HFT's are fast because they have great data feeds AND really fast trading systems - buy-side would not waste the money on the really fast kit as they have nothing they can do with it with the extra millisecond - making no difference to their business. As such I would argue it is in fact not 'unfair' that the buy-side effectively has a slower price feed than HFT. This disparity is a result of the buy-side business model: it is not the fault of the exchange's market data policy to sell data that participants will consume at different speeds.

This is not to say that there is no unfairness here, but simply to point out it is not the exchange's market data products that create the unfairness. The unfairness is the market matching rules that cause it to award liquidity on a 'first in' basis.

> Concerns about fairness break down into at least three sets of potential problems. First, that high frequency trading benefits may essentially be transfers from traditional positional investors, on the one hand, to HFT firms, on the other hand, arising from structural advantages, which transfers redistribute profits from long-term investors to HFT participants (and market infrastructure providers who receive a fee for stratifying data and market access underlying the structural advantages).

Having one type of firm make profit out of another firm, does not make it unfair (well, it feels like it if you're the one losing ;). For it to be unfair it needs to be established that what they are taking out of the intra-day trading 'pool' is more than what they are contributing: eg. liquidity, convenience, risk reduction etc.

> In this regard, an example of note is the claim by Nanex Research that position-neutral HFT (i.e., quasi market making) appears to generate significant net losses to long-term investors. According to this research, HFT results in immaterial price improvement and a net cost to long-term investors measured in billions over the period studied.

You really can't use [http://Nanex Research (who I have the utmost respect for) to frame an argument in Australian equities, other than looking at what Australia may look like if we adopt the same market structure. These guys are great at exposing the crazy things that HFT are getting away with over there, but the markets are completely different as Australia does not have:

* order flow selling / stripping
* massive fragmentation - with one main order book
* market maker centric structure, but direct market access
* quote stuffing (because of tougher regulatory stance + message tax)
* a centralised NBBO (national best bid-offer)
* regulation obligating exchanges to re-route orders

All the above features create opportunities for HFT, and is largely what Nanex are analysing.  Nanex is very US-centric, and doesn't necessarily mean anything for the Australian market. HFT is extremely adaptive - and behaves differently in each market.

> We are not aware of any other segment of society that tolerates the ordinary course making of offers that are not bona fide, to seek to confuse others, or to undermine the infrastructure of commerce.  

Whilst I agree with the general thrust of this statement, I do hesitate on the distinction between seeking 'to confuse others', and seeking 'to protect one-self'. There are many techniques in trading used by buy and sell-side that are specifically intended to prevent others from figuring out what you are doing. To avoid being 'front-run', someone executing a large order will often introduce a lot of random behaviour to avoid others from figuring out what they are doing - and trade in front of them. Is this behaviour seeking to confuse others? Yes. This is one example of a legitimate reason to create confusion.

> Lastly, when it comes to fairness, HFT expands the opportunities to engage in manipulative behaviour that is difficult to detect.  [...] the capacity to police for HFT conduct
has, however, been questioned.

Absolutely. ASIC have a hard enough time keeping up with humans, let alone algorithms. It is frustrating to see algos get away with the same *actions* that humans wouldn't. My view is you want to (1) remove the need for this type of enforcement as possible, by allowing the market to police itself; and (2) have very smart and efficient surveillance for the rest. I think the former can be achieved, in part, by allowing liquidity providers to control their orders better (as already described) plus having exchange-level algorithms made available.

Exchange-implemented algorithms provide a perfect level playing field for all participants, and increase the risk of unwanted execution by those implementing deceptive techniques such as layering. These are essentially 'zero latency' algorithms that cannot be out-paced by HFT firms, and give equal access to all participants.

> Yet that is precisely what is happening when market centres provide selective advance disclosure through co-location, privileged data feeds, and other advantages paid for by high frequency traders

I think the way to refute this claim is via a thought experiment: if you took the feeds of the non-HFT firms and made get their data a *full millisecond* faster than those taking the current 'high speed' ITCH feeds; there would be no impact. Whilst highly automated, technology-focused firms are very sensitive to latency, firms that are driven by human response-times, are not.

It is very appealing to think that there is a conspiracy against the non-HFT firms, in the way that exchanges are dealing with them. Maybe this is the case in the US, but certainly not in Australia. If anything there is a conspiracy of denial by the non-HFT's as to who should do something about the advantage that the HFT's have obtained. Much of the buy side is blaming everyone else (except themselves) - whereas I say much of the blame lie closer to home.

> The rise of HFT has the potential to shift the character of markets, making them more technical and less based on fundamentals.  

Yes, I would argue it is the market rules (combined with fast technology) that creates an environment of advantage for technology-driven trading strategies. HFT is just the strategy that is most profitable in this environment. ie. HFT is the symptom - not the problem.

> With respect to the costs of markets as they perform their capital allocation function, the infrastructure costs underlying HFT are significant.  HFT has produced explosive growth in trades, but even greater growth in quotes or orders (most of which are cancelled).

HFT cannot be blamed for higher numbers of, and smaller, trades. These are driven by algorithmic execution tools (buy-side driven), which are not HFT. There has been no respective explosion in quote numbers in Australia (unlike the US).

> We are not aware of any estimates on a financial system-wide basis of the costs to continually expand capacity, and for market participants to receive and wade through the data.  On top of this would be regulatory costs to surveil this behaviour. We understand that ASIC has increased its budget allocation to electronic trading matters significantly.  Similarly, the opportunity costs of talent and R&D to produce ever-faster market interaction have not
been quantified, but likely are significant.

Absolutely true. At the big picture level -this technology war is just not adding value, and I think it will largely disappear (on the scale we are now seeing) if we take the market rules back to ones that support the natural market (what ISN calls fundamental traders).

> ISN supports ASIC’s efforts to reduce the risk of disruptions to market integrity arising from poorly designed algorithms, including the requirement that market participants using automated trading have appropriate filters and a kill switch.  

I feel the 'kill switch' is flawed policy, for many reasons. For ultra-fast HFT, the switch will be so lightweight (in order to be fast) as to be useless. For the rest, the policy will only be as good as the quality of the kill switch implementation, which of course will vary. A kill switch would not have helped Knight.

My view is that these safety switches need to be implemented at a more trusted level: the executions venues (exchanges). This provides the benefit of no-disadvantage (in terms of speed), and not needing to trust that every participant is doing the right thing. These are tasks best performed at scale, not by every firm individually. It is always the weakest link that will break.
