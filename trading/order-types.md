# Order Types

edgeX offers three order types for perpetual contract trades: Limit Orders, Market Orders, and Conditional Orders.

**1. Limit Order** A limit order allows you to place an order at a specific price or a more favorable price. However, there is no guarantee that a limit order will be filled, as it is only executed when the preferred price is reached. A limit order to buy will only be executed at the limit price or lower, and a limit order to sell will only be executed at the limit price or higher.

Advanced limit order conditions can be set, such as time-in-force options to specify the order expiry time:

* **Fill-or-Kill:** This order must be filled immediately or will be canceled.
* **Good-Till-Time:** This order remains effective until fulfilled or until the maximum default period of 4 weeks is reached.
* **Immediate-or-Cancel:** This order must be executed at the limit price or better immediately, or it will be canceled.

Additionally, you can further customize your order by adding execution conditions with Post-Only or Reduce-Only:

* **Post-Only:** Ensures your order is posted on the order book without being matched immediately, guaranteeing it is only executed as a maker order.
* **Reduce-Only:** Dynamically reduces or adjusts your limit order's contract quantity, ensuring your position is not unintentionally increased.



**2. Market Order** A market order is a buy or sell order that gets filled at the best available price on the market after submission. Market orders are filled based on available liquidity, meaning the order is executed against the limit orders previously placed on the order book.

The execution of a market order is guaranteed, but you cannot specify any prices. You can only specify the contract type and order amount, as all time-in-force and execution conditions are pre-set as a market order.



**3. Conditional Orders** Conditional orders are market or limit orders that have specific conditions attached to them, known as Conditional Market and Conditional Limit orders. This allows traders to set an additional trigger price condition on either market or limit orders.

* **Conditional Market Order:** Unlike market orders, you can set a trigger price with conditional market orders. Once the trigger price is reached, the conditional market order will be filled immediately.
* **Conditional Limit Order:** For a conditional limit order, you need to set two prices: a trigger price and a limit price. When the trigger price meets the last traded price, the order is submitted to the order book to await execution. The order is executed when the limit price, the maximum or minimum price at which you are willing to buy or sell contracts, is reached.
