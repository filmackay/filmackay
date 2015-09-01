---
layout: post
title: "Order flow and toxicity"
date: 2012-08-31 13:41:00
author: Fil
categories:
- blog
- hft
img: hft-chart.gif
thumb: hft-chart.gif
---

(Note: the context of this discussion is short time intervals, and by that I mean shorter than human response times)

There are many different ways to categorise different types of orders, but for our purposes lets put them in buckets of: informed and uninformed. This is the actual terminology used in the firms who deal with order flow.

**Uninformed** order flow are orders created by people/machines who aren't "in the know". They have no unique analysis or advantage over others in the market. For all intents and purposes these orders are pretty random, and not time critical. A human deciding and manually keying in an order to buy a stock in their break at work is a good example of this kind of order flow.

**Informed** order flow are orders that are made by people (read: computers) who are the more informed part of the market. They are more informed for two reasons: they have smarter strategies/methods to predict future prices or they are just faster at processing the publicly available information that everyone else has.

In general the objective of short-term electronic trading is to trade against uninformed order flow as much as possible. This type of order flow is not as smart, and on average will deliver you a profit. Trade against informed order flow, and the odds are seriously stacked against you. These are the orders that all the smart guys avoid, and leave for someone else to pickup.

# How can you tell?


How do you tell the difference between uninformed and informed orders? Well, there's a number of factors here, but mainly: who placed the order, and is the order a good deal for me. One of the benefits of trading via an exchange is anonymity. We are prevented from *knowing* who placed an order, so we are then left to take a guess. based on the available information.

Here are a few techniques for finding uninformed orders:

* Know the source: retail investors create uninformed orders, so if you have a way of identifying the source you're half way there. In the US the idea of "buying order flow" is prevalent - you can pay a retail broker to send you orders first. You get to pick over the bones, with the left overs being sent to the exchange.
* Watch the patterns: spend a lot of money on technology to find patterns, and use this to decide which orders look un/informed.
* Be faster: spend a lot of money on technology to put together information from around the globe, and be the first to grab the slow (now uninformed) orders.
* Other: knowing something else about the source of orders can be as simple as profiling on the basis of the stock, where you know that a particular stock is dominated by retail investors.

# Tale of two markets


The US and Australian equity markets are quite different to one another when it comes to how firms in general exploit order flow:

## United States


Historically US investors have been used to sending orders to market makers, and not having direct access to the order book on an exchange. This allowed retail clients to only take the quotes offered by market makers/specialists, but not to provide quotes themselves. Therefore, a market makers' ability to make profits was linked to the amount of order flow coming from the uninformed sources (over which they have no control), and price pressures from their competitors (which they can). The market maker with the better price and tighter spread would get the business.

What happened next was that firms got aggressive in wanting more exclusive access to this order flow. They did not want to compete on price (which transfers profit to the uninformed investor), so instead they engaged in buying order flow.

This involves paying an uninformed order source (like a retail brokerage) money to send them orders instead of going direct to the specialists/market makers - potentially subsidising the brokerage rates of the retail brokers as they sought out more 'uninformed investors'. This allows them to have first right of refusal of any orders, before it is exposed to the wider market via some kind of exchange. They are aware, for example, if there has been a slight dip in an overseas market or a similar stock, the instant an order comes in from a retail client for a security. This allows them the exclusive option to take or leave the order depending on whether it is a good deal for them. This is called [adverse selection](http://en.wikipedia.org/wiki/Adverse_selection).

## Australia


In Australia, we have always been more used to having direct access to the central limit book in that the market was not dominated by [market makers](http://en.wikipedia.org/wiki/Market_maker). In order to obtain access to the uninformed order flow, firms had to compete in an open, transparent and competitive market on the [ASX](http://www.asx.com.au).

In order to gain exclusive access to retail order flow [over-the-counter](http://en.wikipedia.org/wiki/Over-the-counter_(finance)) [CFD providers](http://en.wikipedia.org/wiki/Contract_For_Difference) emerged. They were able to achieve the same thing - get access to the unformed order flow, without having to compete for the business on a price basis. They can choose which trades to take on, and which to effectively pass through to the exchanges. Knowing the client (thanks to regulations requiring them to establish investor "suitability") allows them to drill further into analytics on clients, and look at other clues to determine patterns of which clients may or be profitable to bet against.

# Toxic order flow


What we have today is a market that is very efficient at removing uninformed orders. Unfortunately this creates order flow residual that only contains informed order flow, or 'toxic order flow'. It are the orders that you don't want to trade against (if your objective is to make a profit).

Order flow toxicity is one postulated contributing factor to the [2010 flash crash](http://en.wikipedia.org/wiki/2010_Flash_Crash), since the levels in the hour prior to the crash were quite high. High toxicity means market makers are losing money, and withdraw from the market to protect themselves from further losses. This loss of liquidity then leads to increased volatility and larger price movements.

There are measures for order flow toxicity such as [VPIN](http://en.wikipedia.org/wiki/VPIN); which calculates the probability that orders are informed. You can think of retail order flow being near 0, and orders from a know-all computer with really smart predictive capability being near 1. Some have [proposed](http://www.iijournals.com/doi/abs/10.3905/jot.2012.7.2.009) monitoring VPIN in the US in real-time, with the SEC estimating it would cost several billion dollars per year just to do that.
