# Private WebSocket

This document describes the spot market private WebSocket interface.

## Base URL

```text
wss://spot-quote.edgex.exchange/api/v1/private/ws
```

## Endpoint

| Path | Description |
| --- | --- |
| `/api/v1/private/ws` | Private account and trading WebSocket endpoint. |

## Description

- Authentication is required during the WebSocket handshake.
- After the connection is established, the server returns `connected`.
- The gateway then loads account snapshot data and pushes it immediately.
- This endpoint does not use subscribe or unsubscribe operations.
- Account and trading updates are pushed automatically after the connection is established.
- The server sends heartbeat `ping` messages every 10 seconds. The client should reply with `pong` using the same `time` value.
- The client can also send `ping` and receive a matching `pong`.
- Repeated invalid messages may cause the server to close the session.

## Authentication

The current implementation accepts private WebSocket authentication during the handshake.

Supported modes:

1. API key headers: `x-api-key`, `x-passphrase`, `x-signature`, `x-timestamp`
2. Encoded `Sec-WebSocket-Protocol` payload carrying the same authentication fields
3. ECDSA signature mode using `x-api-signature` and `x-api-timestamp` with the `accountId` query parameter

In the standard API key flow, the gateway resolves the authenticated user's `spot-main` account and binds the session to that account.

## Common Response Envelope

```json
{
  "sid": "optional-session-id",
  "type": "connected",
  "content": {},
  "time": "optional-timestamp"
}
```

## Response Types

| Type | Description |
| --- | --- |
| `connected` | Connection established. |
| `ping` | Server heartbeat. |
| `pong` | Pong response. |
| `error` | Invalid request or authentication-related error. |
| `trade-event` | Account and trading updates. |
| `assets-event` | Asset updates. |

## Connection Established Example

```json
{
  "sid": "ee6f8914-4765-cdba-3e93-0bead42583b7",
  "type": "connected",
  "time": "1776225301253"
}
```

## Client Ping Example

```json
{
  "type": "ping",
  "time": "1776225301253"
}
```

## Pong Example

```json
{
  "type": "pong",
  "time": "1776225301253"
}
```

## Snapshot Push

After the connection is established, the gateway pushes a `trade-event` snapshot.

```json
{
  "sid": "ee6f8914-4765-cdba-3e93-0bead42583b7",
  "type": "trade-event",
  "content": {
    "event": "Snapshot",
    "version": 1000,
    "data": {
      "account": [
        {
          "id": "10001",
          "userId": "20001",
          "clientAccountId": "spot-main",
          "isSystemAccount": false,
          "defaultFeeSetting": {},
          "symbolIdToFeeSetting": {},
          "createOrderRateLimitPerMinute": 0,
          "createOrderDelayMilliseconds": 0,
          "extraType": "",
          "extraDataJson": "",
          "status": "ACCOUNT_STATUS_NORMAL",
          "createdTime": "1776225200000",
          "updatedTime": "1776225300000"
        }
      ],
      "balance": [
        {
          "accountId": "10001",
          "coinId": "7",
          "amount": "1234.56000000",
          "pendingDepositAmount": "0",
          "pendingWithdrawAmount": "0",
          "pendingTransferInAmount": "0",
          "pendingTransferOutAmount": "0",
          "cumDepositAmount": "10000",
          "cumWithdrawAmount": "0",
          "cumTransferInAmount": "0",
          "cumTransferOutAmount": "0",
          "cumTradeInAmount": "12.5",
          "cumTradeOutAmount": "1.2",
          "cumOrderFillFeeIncomeAmount": "0.01",
          "createdTime": "1776225200000",
          "updatedTime": "1776225300000"
        }
      ],
      "asset": [
        {
          "accountId": "10001",
          "coinId": "7",
          "accountEquity": "1234.56000000",
          "accountAvailable": "1200.00000000",
          "accountFrozen": "34.56000000",
          "accountBuySize": "12.50000000",
          "accountAvgPrice": "2379.95000000"
        }
      ],
      "order": [
        {
          "id": "90001",
          "accountId": "10001",
          "symbolId": "90000002",
          "baseCoinId": "2",
          "quoteCoinId": "7",
          "orderSide": "BUY",
          "price": "2379.95",
          "size": "0.10000000",
          "value": "237.99500000",
          "clientOrderId": "spot-order-001",
          "type": "LIMIT",
          "timeInForce": "GTC",
          "reduceOnly": false,
          "triggerPrice": "0",
          "isPositionTpsl": false,
          "orderSource": "ORDER_SOURCE_API",
          "openTpslParentOrderId": "0",
          "isSetOpenTp": false,
          "openTpParam": null,
          "isSetOpenSl": false,
          "openSlParam": null,
          "extraType": "",
          "extraDataJson": "",
          "takerFeeRate": "0.0005",
          "makerFeeRate": "0.0002",
          "feeDiscount": "1",
          "takerFeeDiscount": "1",
          "makerFeeDiscount": "1",
          "status": "ORDER_STATUS_OPEN",
          "matchSequenceId": "0",
          "triggerTime": "0",
          "triggerPriceTime": "0",
          "triggerPriceValue": "0",
          "cancelReason": "ORDER_CANCEL_REASON_UNSPECIFIED",
          "latestFillPrice": "0",
          "maxFillPrice": "0",
          "minFillPrice": "0",
          "cumFillSize": "0",
          "cumFillValue": "0",
          "cumFillFee": "0",
          "createdTime": "1776225200000",
          "updatedTime": "1776225300000"
        }
      ]
    },
    "time": 1776225301253
  }
}
```

Snapshot payloads may contain `account`, `balance`, `asset`, and `order`. Empty collections may be omitted.

## Event Data Rules

The exact objects in `content.data` depend on the event type.

| Event | Typical Data |
| --- | --- |
| `Snapshot` | `account`, `balance`, `asset`, `order` |
| `account-update` | `account` |
| `deposit-update` | `deposit`, `balance`, `balanceTransaction` |
| `withdraw-update` | `withdraw`, `balance`, `balanceTransaction` |
| `transfer-in-update` | `transferIn`, `balance`, `balanceTransaction` |
| `transfer-out-update` | `transferOut`, `balance`, `balanceTransaction` |
| `order-update` | `order`, `balance`, `balanceTransaction`, `orderFillTransaction` |
| `order-fee-income` | `balance`, `balanceTransaction` |
| `unknown` | Fallback event type |

## Trade Event Example

```json
{
  "type": "trade-event",
  "content": {
    "event": "order-update",
    "version": 1001,
    "data": {
      "order": [
        {
          "id": "90001",
          "accountId": "10001",
          "symbolId": "90000002",
          "baseCoinId": "2",
          "quoteCoinId": "7",
          "orderSide": "BUY",
          "price": "2379.95",
          "size": "0.10000000",
          "value": "237.99500000",
          "clientOrderId": "spot-order-001",
          "type": "LIMIT",
          "timeInForce": "GTC",
          "status": "ORDER_STATUS_FILLED",
          "latestFillPrice": "2379.95",
          "cumFillSize": "0.10000000",
          "cumFillValue": "237.99500000",
          "cumFillFee": "0.04759900",
          "createdTime": "1776225200000",
          "updatedTime": "1776225301253"
        }
      ],
      "balance": [
        {
          "accountId": "10001",
          "coinId": "7",
          "amount": "996.51740100",
          "pendingDepositAmount": "0",
          "pendingWithdrawAmount": "0",
          "pendingTransferInAmount": "0",
          "pendingTransferOutAmount": "0",
          "cumDepositAmount": "10000",
          "cumWithdrawAmount": "0",
          "cumTransferInAmount": "0",
          "cumTransferOutAmount": "0",
          "cumTradeInAmount": "12.6",
          "cumTradeOutAmount": "1.2",
          "cumOrderFillFeeIncomeAmount": "0.01",
          "createdTime": "1776225200000",
          "updatedTime": "1776225301253"
        }
      ],
      "balanceTransaction": [
        {
          "id": "70001",
          "accountId": "10001",
          "coinId": "7",
          "type": "ORDER_FILL",
          "deltaAmount": "-237.99500000",
          "afterAmount": "996.51740100",
          "fillSize": "0.10000000",
          "fillValue": "237.99500000",
          "fillFee": "0.04759900",
          "version": "1001",
          "orderId": "90001",
          "orderFillTransactionId": "80001",
          "symbolId": "90000002",
          "createdTime": "1776225301253",
          "updatedTime": "1776225301253"
        }
      ],
      "orderFillTransaction": [
        {
          "id": "80001",
          "accountId": "10001",
          "symbolId": "90000002",
          "baseCoinId": "2",
          "quoteCoinId": "7",
          "orderId": "90001",
          "orderSide": "BUY",
          "fillSize": "0.10000000",
          "fillValue": "237.99500000",
          "fillFee": "0.04759900",
          "direction": "TAKER",
          "version": "1001",
          "tradeInBalanceTransactionId": "0",
          "tradeOutBalanceTransactionId": "70001",
          "matchSequenceId": "123456789",
          "matchIndex": 0,
          "matchTime": "1776225301253",
          "matchAccountId": "10002",
          "matchOrderId": "90002",
          "matchFillId": "fill-001",
          "extraType": "",
          "extraDataJson": "",
          "createdTime": "1776225301253",
          "updatedTime": "1776225301253"
        }
      ]
    },
    "time": 1776225301253
  }
}
```
