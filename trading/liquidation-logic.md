# Liquidation Logic

edgeX employs Oracle Price to prevent liquidations triggered by low liquidity or market manipulation.

In cross margin mode, a position is liquidated when the available balance reaches zero and the position margin drops to the maintenance margin level.
