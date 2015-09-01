---
layout: post
title: "TimeMatch Examples"
date: 2012-09-05
author: Fil
categories:
- blog
- TimeMatch
img: hft-chart.gif
thumb: hft-chart.gif
---
<style>
.orderbook tr {
    vertical-align: text-top
}

.orderbook .potential {
    background-color: LightGrey;
}

.orderbook .hopeful {
    background-color: Yellow;
}

.orderbook .auction {
    background-color: Orange;
}

.orderbook .trade {
    background-color: LightGreen;
}
</style>

Here are some examples of how the TimeMatch public order book would work. You may want review the premise of this design in the previous posts, as well as the terminology. The following key is used to interpret the status of various orders in the examples:

<table class="orderbook">
    <tr>
        <th>Order Status:</th>
        <th>Cancel</th>
        <th>Uncertain</th>
        <th>Improvement</th>
        <th>Notes</th>
    </tr>
    <tr>
        <td>Quote</td>
        <td>Yes</td>
        <td>Yes</td>
        <td>Yes</td>
        <td>Uncommitted quote</td>
    </tr>
    <tr>
        <td class="potential">Potential</td>
        <td>Yes</td>
        <td>Yes</td>
        <td>Yes</td>
        <td>Potentially matching against another order, if the market is stationary.</td>
    </tr>
    <tr>
        <td class="hopeful">Hopeful</td>
        <td>No</td>
        <td>Yes</td>
        <td>Yes</td>
        <td>Order is committed to the auction, but they could involuntarily be removed if another bidder offers a better price, with sufficient time period.</td>
    </tr>
    <tr>
        <td class="auction">Auction</td>
        <td>No</td>
        <td>No</td>
        <td>Yes</td>
        <td>Order will match against the opposing Hopeful order, or another order at a higher price.</td>
    </tr>
    <tr>
        <td class="trade">Trade</td>
        <td>No</td>
        <td>No</td>
        <td>No</td>
        <td>Order is executed and complete on both sides</td>
    </tr>
</table>

## A: Status quo

We'll start with a simple example that shows the way the public order book works today - ie. instant execution with no auction period:

<table class="orderbook">
<tr>
<th>Time</th>
<th>Buy</th>
<th>Sell</th>
<th>Trade</th>
</tr>
<tr>
<td>0.000</td>
<td style="text-align: right"></td>
<td><span class="quote">10 (0) Z</span></td>
<td></td>
</tr>
<tr>
<td>0.001</td>
<td style="text-align: right"><span class="trade">X (0) 10</span></td>
<td><span class="trade">10 (0) Z</span></td>
<td>Z <span class="glyphicon glyphicon-arrow-right"></span> X @ 10</td>
</tr>
<tr>
<td>0.001</td>
<td></td>
<td></td>
<td></td>
</tr>
</table>

The above table shows an order book a seller "Z" showing an order which is matched up a millisecond later by "X". Both parties are asking for instant execution - denoted by "(0)" in both cases which means the auction time period is zero. The "10" is the price in both cases, so we have the simplest of trade matches.

## B: Slow liquidity provider

<table class="orderbook">
    <tr>
    <th>Time</th>
    <th>Buy</th>
    <th>Sell</th>
    <th>Trade</th>
    </tr>
    <tr>
    <td>0.000</td>
    <td style="text-align: right"></td>
    <td><span class="quote">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.001</td>
    <td style="text-align: right"><span class="potential">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>1.001</td>
    <td style="text-align: right"><span class="trade">X (0) 10</span></td>
    <td><span class="trade">10 (1) Z</span></td>
    <td>Z <span class="glyphicon glyphicon-arrow-right"></span> X @ 10</td>
    </tr>
    <tr>
    <td>1.001</td>
    <td style="text-align: right"></td>
    <td></td>
    <td></td>
    </tr>
</table>

Here we have a mismatch of time periods: the seller wants to trade on a 1 second auction, whereas the buyer wants to trade instantly. In this case, since the market is stationary, the order book will match them up as nothing has occurred in the intervening second. There is no 'auction' per-se in this situation, and someone could have jumped over the top of buyer "Z" at any time up to the match. This type of "stationary non-auction" scenario is present to merely provide natural liquidity between investor types when nothing is moving and there is no additional time period risk to the liquidity creator.


## C: Fast liquidity provider


<table class="orderbook">
    <tr>
    <th>Time</th>
    <th>Buy</th>
    <th>Sell</th>
    <th>Trade</th>
    </tr>
    <tr>
    <td>0.000</td>
    <td style="text-align: right"><span class="quote">Z (0) 10</span></td>
    <td></td>
    <td></td>
    </tr>
    <tr>
    <td>0.001</td>
    <td style="text-align: right"><span class="trade">Z (0) 10</span></td>
    <td><span class="trade">10 (1) X</span></td>
    <td>X <span class="glyphicon glyphicon-arrow-right"></span> Z @ 10</td>
    </tr>
    <tr>
    <td>0.001</td>
    <td style="text-align: right"></td>
    <td></td>
    <td></td>
    </tr>
</table>

The liquidity creator Z has requested instant execution. Liquidity taker X then enters with an exposure period of up to 1 second. This match is done instantly since the taker's time period is greater than or equal to the liquidity creator's. Since there is no adverse selection of the slower order (since it arrived later), this is ruled to not expose them.

Of course there is some potential for latency arbitrage here if you *know* that X is about to hit the order book. This is an issue that can be addressed - and an area for further refinement.

## D: Slow jumps in front of fast

<table class="orderbook">
    <tr>
    <th>Time</th>
    <th>Buy</th>
    <th>Sell</th>
    <th>Trade</th>
    </tr>
    <tr>
    <td>0.000</td>
    <td style="text-align: right"></td>
    <td><span class="quote">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.001</td>
    <td style="text-align: right"><span class="potential">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.002</td>
    <td style="text-align: right"><span class="hopeful">Y (1) 10</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>1.002</td>
    <td style="text-align: right"><span class="trade">Y (1) 10</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="trade">10 (1) Z</span></td>
    <td>Z <span class="glyphicon glyphicon-arrow-right"></span> Y @ 10</td>
    </tr>
    <tr>
    <td>1.002</td>
    <td style="text-align: right"><span class="quote">X (0) 10</span></td>
    <td></td>
    <td></td>
    </tr>
</table>

In this example buyer X has come in to take Z's liquidity, but is not willing to bid in an auction - only willing to trade immediately. At this point Z does not know whether X is more informed. Immediately after this, Y jumps in front of X on the queue and is willing to submit to an auction of 1 second, which is good enough for Z. A 1-second auction is started, and since no-one out-bids Y with a higher price the trade is matched. X is left unfilled.

## E: Price divergence on latency


<table class="orderbook">
    <tr>
    <th>Time</th>
    <th>Buy</th>
    <th>Sell</th>
    <th>Trade</th>
    </tr>
    <tr>
    <td>0.000</td>
    <td style="text-align: right"></td>
    <td><span class="quote">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.001</td>
    <td style="text-align: right"><span class="potential">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.002</td>
    <td style="text-align: right"><span class="hopeful">Y (1) 10</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.003</td>
    <td style="text-align: right"><span class="quote">X (0) 11</span><br />
    <span class="hopeful">Y (1) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>1.002</td>
    <td style="text-align: right"><span class="quote">X (0) 11</span><br />
    <span class="trade">Y (1) 10</span></td>
    <td><span class="trade">10 (1) Z</span></td>
    <td>Z <span class="glyphicon glyphicon-arrow-right"></span> Y @ 10</td>
    </tr>
    <tr>
    <td>1.002</td>
    <td style="text-align: right">X (0) 11</td>
    <td></td>
    <td></td>
    </tr>
</table>


In this example there is a strange situation where the price divergence on the basis of latency. While a fast trader outbids a slower one on a price basis, they are not willing to commit to an auction. Price improvement cannot be passed on to Z in this case because doing so would encourage late and informed orders to arrive at the end of auctions - handing them the advantage of adversely selecting their opponents. In this scenario Y was granted the match at a lower price due to the fact they committed to the auction first, thereby rewarding them for their willingness to expose themselves to the auction.

## F: Fast traders not held up by slow ones


<table class="orderbook">
    <tr>
    <td>Time</td>
    <td>Buy</td>
    <td>Sell</td>
    <td>Trade</td>
    </tr>
    <tr>
    <td>0.000</td>
    <td style="text-align: right"></td>
    <td>10 (1) Z</td>
    <td></td>
    </tr>
    <tr>
    <td>0.001</td>
    <td style="text-align: right"><span class="potential">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.002</td>
    <td style="text-align: right"><span class="hopeful">Y (1) 10</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.500</td>
    <td style="text-align: right"><span class="hopeful">Y (1) 10</span><br />
    <span class="quote">X (0) 08</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.501</td>
    <td style="text-align: right"><span class="hopeful">Y (1) 10</span><br />
    <span class="quote">X (0) 08</span></td>
    <td><span class="quote">09 (0) W</span><br />
    <span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.600</td>
    <td style="text-align: right"><span class="hopeful">Y (1) 10</span><br />
    <span class="trade">X (0) 08</span></td>
    <td><span class="trade">08 (0) W</span><br />
    <span class="auction">10 (1) Z</span></td>
    <td>W <span class="glyphicon glyphicon-arrow-right"></span> X @ 8</td>
    </tr>
    <tr>
    <td>0.600</td>
    <td style="text-align: right"><span class="hopeful">Y (1) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>1.002</td>
    <td style="text-align: right"><span class="trade">Y (1) 10</span></td>
    <td><span class="trade">10 (1) Z</span></td>
    <td>Z <span class="glyphicon glyphicon-arrow-right"></span> Y @ 10</td>
    </tr>
</table>


The scenario shows where fast prices can move throughout auctions for slow trades. Here the price drops *and executes* while an auction is still in progress - with different prices.  The trades come out in a different order to the order instructions that generated them. We can see here that traders are not held-up at all by slower traders, they all progress concurrently.

## G: Price improvement


<table class="orderbook">
    <tr>
    <td>Time</td>
    <td>Buy</td>
    <td>Sell</td>
    <td>Trade</td>
    </tr>
    <tr>
    <td>0.000</td>
    <td style="text-align: right"></td>
    <td><span class="quote">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.001</td>
    <td style="text-align: right"><span class="potential">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>0.500</td>
    <td style="text-align: right"><span class="potential">Y (0) 11</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>1.100</td>
    <td style="text-align: right"><span class="potential">W (0) 12</span><br />
    <span class="quote">Y (0) 11</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>2.000</td>
    <td style="text-align: right"><span class="potential">V (0) 14</span><br />
    <span class="quote">W (0) 12</span><br />
    <span class="quote">Y (0) 11</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>2.500</td>
    <td style="text-align: right"><span class="potential">W (0) 12</span><br />
    <span class="quote">Y (0) 11</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="potential">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>3.000</td>
    <td style="text-align: right"><span class="hopeful">U (1) 13</span><br />
    <span class="quote">W (0) 12</span><br />
    <span class="quote">Y (0) 11</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>3.500</td>
    <td style="text-align: right"><span class="quote">W (0) 14</span><br />
    <span class="hopeful">U (1) 13</span><br />
    <span class="quote">Y (0) 11</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>3.600</td>
    <td style="text-align: right"><span class="quote">W (0) 15</span><br />
    <span class="hopeful">Y (1) 14</span><br />
    <span class="quote">U (1) 13</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>4.000</td>
    <td style="text-align: right"><span class="hopeful">W (1) 15</span><br />
    <span class="quote">Y (1) 14</span><br />
    <span class="quote">U (1) 13</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>4.500</td>
    <td style="text-align: right"><span class="hopeful">W (1) 15</span><br />
    <span class="quote">Y (1) 11</span><br />
    <span class="quote">U (1) 10</span><br />
    <span class="quote">X (0) 10</span></td>
    <td><span class="auction">10 (1) Z</span></td>
    <td></td>
    </tr>
    <tr>
    <td>5.000</td>
    <td style="text-align: right"><span class="trade">W (1) 15</span><br />
    <span class="quote">U (1) 10</span><br />
    <span class="quote">X (0) 10</span><br />
    <span class="quote">Y (1) 09</span></td>
    <td><span class="trade">10 (1) Z</span></td>
    <td>Z <span class="glyphicon glyphicon-arrow-right"></span> W @ 15</td>
    </tr>
    <tr>
    <td>5.000</td>
    <td style="text-align: right"><span class="quote">U (1) 10</span><br />
    <span class="quote">X (0) 10</span><br />
    <span class="quote">Y (1) 09</span></td>
    <td></td>
    <td></td>
    </tr>
</table>

This is a fairly typical latency arbitrage scenario, where a liquidity creator Z is exposed by news creating bidding amongst liquidity takers. Instead of handing the order to the fastest trader, the order book requires takers to commit to a time period before allowing them to lock an auction in. Prior to the auction being called there are no executions, despite overlapping price since the market is not stationary.
