# Trading Accounts & Margin

**Collateral:** edgeX supports USDT as the primary collateral for trading.



**Margin Mode and Trading Accounts:** By default, edgeX operates with a cross-margin system, allowing collateral to be shared among all positions within a single trading account. Users can also opt for isolated margins by creating separate trading accounts under the same wallet using the sub-accounts feature.

Users can establish up to 20 trading accounts with independent margins per single wallet. The liquidation of one trading account does not affect the liquidation of other trading accounts associated with the same wallet.

Transfers of Available Balance for Withdrawals (as defined below) between trading accounts are fee-free. However, such transfers can impact the margin ratio and potentially trigger liquidation for the involved accounts.

For comprehensive details on the liquidation process, please refer to the Liquidation Logic section.



**Margin, Profit & Loss (P\&L) Calculations:** For USDT Perpetual Contracts, margin and P\&L are calculated in USDT. This eliminates the need for traders to hedge their positions against non-stablecoin cryptocurrency risks. The P\&L chart follows a linear curve; for instance, if the price moves by 100 USDT when trading 1 BTC, the trader's P\&L will see a change of 100 USDT.



**Hedge Mode:** Users can create sub-accounts to emulate Hedge Mode behavior, allowing them to simultaneously open long and short positions in the same market.
