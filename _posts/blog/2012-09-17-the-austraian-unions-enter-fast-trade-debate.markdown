---
layout: post
title: "The Australian: Unions enter fast-trade debate"
date: 2012-09-17
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---
The Australian ran a [piece](http://www.theaustralian.com.au/business/financial-services/unions-enter-fast-trade-debate/story-fn91wd6x-1226473766705) on the [ACTU](http://www.actu.org.au/), apparently calling for an end to HFT. Well that was unexpected!

## Points of confusion?

I usually try to start with the parts of a story I agree with, but lets just start with a part that I'm confused about:

> [...] Australian Securities Exchange chief executive Elmer Funke Kupper this week said he wanted to "tighten the economics of the practice" to make it less profitable.

I've seen this quote a bit since the interview it came from, but I'm really interested: how will you make it less profitable? By charging them more (and become a de-facto partner), or by enabling the traders they make money from, to avoid giving it away. I'd argue that [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}) achieves the latter.

## Points of discussion?

> [...] market operator Chi-X has helped to enable the trend towards HFT, Australian Securities Exchange chief executive Elmer Funke Kupper [...]

Chi-X has not helped HFT any more than the ASX, who actually have trading platform dedicated to it (PureDeal) plus extensive infrastructure to support their operation (ALC). Not sure you can point fingers on that one towards Chi-X, I think the more accurate message is: market fragmentation (caused by competition) has helped to enable the trend towards HFT.

> The ACTU will join the debate today by seeking a moratorium on all high-frequency trading, so that the regulator can do a full study of the costs and benefits of the practice. Failing that, the peak union body wants to stop the very fastest trades by imposing a "minimum resting time" of one second for all transactions on Australian markets.

Minimum resting times (stopping traders from canceling orders until one second after the order was created) wont really do much to curb the ill-effects of HFT in Australia. This would make a massive difference in the US (though one second would create a lot of unintended consequences) to eliminate [quote stuffing](http://www.investopedia.com/terms/q/quote-stuffing.asp), but we don't have those issues in Australia.

The detrimental HFT activity in Australia is more characterised by the speed of an HFT trader responding to an order that appears from a non-HFT trader: called 'taking liquidity'. As I've blogged about with my [TimeMatch]({% post_url blog/2012-09-04-timematch-a-slower-order-book %}) scheme, this race creates no value for anyone except the HFT trader. It does not create the traditional benefit of greater market participation: increased competition (read: better prices for the non-HFT trader).

My personal view, a one second minimum resting time would be a disaster and make the HFT situation worse. This scheme actually exposes traders even more to other HFT predators who know that other traders are unable to remove their orders when they want to, within that second. In other words, the good HFT would be penalised, and the bad HFT would be rewarded. Go figure!

> Another recommendation in the ACTU's formal submission to ASIC, obtained by The Australian, is a ban on "flash orders", in which traders gain advance notice of incoming orders, buy up stock ahead of the imminent purchase and sell them to the buyer.

[Flash orders](http://en.wikipedia.org/wiki/Flash_trading) are bad things, I agree - but they don't exist in Australia.

My somewhat cynical view of them (in the US) is that they really are a by-product of badly designed market regulation, not the pure invention of HFT's. One example of how rules intended to help you, can end up harming once you realise that light does not travel at infinity.

> It says additional fees should also be imposed on HFT operators who cancel orders regularly, seen as a common tactic by traders moving in and out of the market very quickly.

Traders moving quickly is not necessarily a bad thing, it can just mean they are being more efficient and able to (in the case of a market maker) able to quote tighter buy/sell spreads. This kind of crude mechanism should be at the end of a very long list of things we should try first, the simplest being allow the market itself to decide how fast *it* wants to operate.
