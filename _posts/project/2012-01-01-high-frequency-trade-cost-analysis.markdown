---
layout: project
title:  High Frequency Trade Cost Analysis
when:   2012-2014
model:  Custom built
tech:   C++, Python, Pandas
categories:
- project
img: high-frequency-trade-cost-analysis.jpg
thumb: high-frequency-trade-cost-analysis.jpg
carousel:
- high-frequency-trade-cost-analysis.png
client: Capital Markets CRC, Confidential
---
#### High Frequency TCA

This project involved the analysis of detailed high-frequency trade data, including analysis if a key missing data point: time. Investigating the myriad of clocks and synchronisation structures used in the capital markets, seemingly random behaviour became clearer. Supplementing this with proprietary order flow data allowed trade interactions to be classified in terms of informedness, allowing the identification of low-latency predatory traders.

This analysis formed the basis of a HF-TCA methodology that allows any order flow to be classified in terms of it's interaction with more informed traders. Providing the following metrics:

* Latency curve: how much alpha is being lost due to implementation latency
* Clustering: identification of particular concentrations of leakage, in terms of implementation factors such as market, time of day, asset class, broker or execution algorithm.
* Leakage: how much is being lost, providing the basis for a business case to improve pure latency outcomes.
* Trade costs: what is the implicit costs (at high-frequency timeframes) being paid, and how significant are they compared with explicit brokerage?

The above methodology was also used to identify informed order flow, and calculate an overall rent that the market pays to such traders - for liquidity that would otherwise find a natural counterparty.
