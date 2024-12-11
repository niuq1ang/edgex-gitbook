# Funding Fees

Funding fees are a mechanism designed to ensure that the price of perpetual futures contracts aligns closely with the underlying asset's spot market price. These fees are periodically exchanged between traders holding long and short positions to incentivize the convergence of the contract price with the spot price.



Mechanism of Funding Fees

Funding fees are exchanged every hour between holders of long and short positions. The funding rate, which dictates the fee exchange, fluctuates in real-time. When the funding rate is positive at the time of settlement, long position holders pay the funding fees to short position holders. Conversely, when the funding rate is negative, short position holders pay the fees to long position holders. Only traders holding positions at the time of settlement are liable to either pay or receive funding fees. The calculation of the funding fees is based on the value of the position at the time of settlement, using the formula:

_**Funding Fees=Position Value×Index Price×Funding Rate**_



**Funding Rate Calculation**&#x20;

The funding rate consists of two parts: **Interest Rate** and **Average Premium Index (P)**.

edgeX calculates the **Interest Rate (I)** and the **Average Premium Index (P)** every minute by performing an N\*-Hour Time-Weighted-Average-Price (TWAP) over the series of minute rates. The closer to the funding fee settlement time, the greater the coefficient of the premium index.

Taking an 4-hour funding interval as an example, the Average Premium Index (P) is calculated using the formula: (Premium Index \_1 \* 1 + Premium Index \_2 \* 2 +... + Premium Index \_240 \* 240)/(1 + 2 +... + 240).

Each hour corresponds to 60-minute intervals. If the funding interval is every 4 hours, corresponding to 240 intervals (4 \* 60), then the coefficients would be 1, 2, ..., 240, forming an arithmetic progression starting from 1 with a common difference of 1.

The Funding Rate is next calculated with the N\*-Hour Interest Rate component and the N\*-Hour premium/discount component. A +/−0.05% dampener is added.

\*N = Funding Time interval. Suppose funding occurs once every 4 hours, N = 4. And if funding occurs once per hour, N = 1.

Funding Rate (F) = Average Premium Index (P) + clamp (Interest Rate (I) − Average Premium Index (P), 0.05%, −0.05%)

Hence, if (I − P) is within +/−0.05%, then F = P + (I − P) = I. In other words, the funding rate will equal the Interest Rate.

This calculated funding rate is then applied to a trader’s position value to determine the funding fee to be paid or received at the funding timestamp



**Interest Rate (I)**

Formula

Interest Rate (I) = Price Interest Rate Index − Base Rate Index/Fund Rate Interval

* Interest Quote Index = The interest rate for borrowing the quoted currency
* Interest Base Index = The interest rate for borrowing the base currency
* Funding Interval = 24/Funding Time interval



**Premium Index (P)**

Formula

Premium Index (P) = \[Max (0, Impact Bid Price − Index Price) − Max (0, Index Price − Impact Ask Price)]/Index Price

\* Impact Bid Price = The average fill price to execute the Impact Margin Notional on the Bid side

\* Impact Ask Price = The average fill price to execute the Impact Margin Notional on the Ask side

**Impact Margin Notional** (IMN) is the notion available to trade with a certain amount of margin. It’s used to determine how deep the order book is and to measure the Impact Bid or Ask Price.



















