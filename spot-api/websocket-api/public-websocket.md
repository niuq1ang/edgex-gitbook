# Public WebSocket

This document describes the spot market public WebSocket interface.

## Base URL

```text
wss://spot-quote.edgex.exchange/api/v1/public/ws
```

## Endpoint

| Path | Description |
| --- | --- |
| `/api/v1/public/ws` | Public market data WebSocket endpoint. |

The spot private WebSocket endpoint `/api/v1/private/ws` is documented separately.

## Description

- Subscribe and unsubscribe requests use JSON messages such as `{"type":"subscribe","channel":"ticker.90000002"}`.
- The gateway validates channels on subscribe and unsubscribe. Invalid channels return an `error` message.
- After a successful subscribe request, the server returns `subscribed` and then pushes snapshot data for that channel.
- Market data payloads use `Snapshot` for initial data and `changed` for subsequent updates.
- The server may send `ping` heartbeats. The client should reply with `pong` using the same `time` value.
- The client can also send `ping` and receive a matching `pong`.
- Repeated invalid messages may cause the server to close the session.

## Common Response Envelope

```json
{
  "sid": "optional-session-id",
  "type": "connected",
  "channel": "optional-channel",
  "request": "optional-original-request-json-string",
  "content": {},
  "time": "optional-timestamp"
}
```

## Response Types

| Type | Description |
| --- | --- |
| `connected` | Connection established. |
| `subscribed` | Subscription accepted. |
| `unsubscribed` | Unsubscription accepted. |
| `ping` | Server heartbeat. |
| `pong` | Pong response. |
| `error` | Invalid request or invalid channel. |
| `quote-event` | Market data payload. |

## Connection Established Example

```json
{
  "sid": "ee6f8914-4765-cdba-3e93-0bead42583b7",
  "type": "connected",
  "time": "1776225301253"
}
```

## Error Example

Typical gateway error codes include:

- `GATEWAY_UNRECOGNIZED_MESSAGE`
- `GATEWAY_INVALID_MESSAGE_TYPE`
- `GATEWAY_INVALID_CHANNEL`
- `GATEWAY_INVALID_INSTRUMENT_ID`
- `GATEWAY_INVALID_KLINE_PRICE_TYPE`
- `GATEWAY_INVALID_KLINE_INTERVAL`
- `GATEWAY_INVALID_BOOK_DEPTH`
- `GATEWAY_LOAD_SNAPSHOT_DATA_ERROR`

```json
{
  "type": "error",
  "request": "{\"type\":\"subscribe\",\"channel\":\"depth.invalid.15\"}",
  "content": {
    "code": "GATEWAY_INVALID_CHANNEL",
    "msg": "invalid channel : depth.invalid.15"
  }
}
```

## Metadata

### Request

```json
{
  "type": "subscribe",
  "channel": "metadata"
}
```

### Response

```json
{
  "type": "subscribed",
  "channel": "metadata",
  "request": "{\"type\":\"subscribe\",\"channel\":\"metadata\"}"
}
```

### Payload

```json
{
  "type": "quote-event",
  "channel": "metadata",
  "content": {
    "channel": "metadata",
    "dataType": "Snapshot",
    "data": [
      {
        "global": {},
        "coinList": [],
        "symbolList": [],
        "multiChain": null
      }
    ]
  }
}
```

## Subscribe to 24-Hour Ticker

### Channel Description

| Channel | Description |
| --- | --- |
| `ticker.{instrumentId}` | Subscribe to one instrument ticker. |
| `ticker.all` | Subscribe to all instrument tickers. |
| `ticker.all.1s` | Subscribe to periodic aggregate ticker pushes. |

### Request

```json
{
  "type": "subscribe",
  "channel": "ticker.90000002"
}
```

### Response

```json
{
  "type": "subscribed",
  "channel": "ticker.90000002",
  "request": "{\"type\":\"subscribe\",\"channel\":\"ticker.90000002\"}"
}
```

### Payload

```json
{
  "type": "quote-event",
  "channel": "ticker.90000002",
  "content": {
    "channel": "ticker.90000002",
    "dataType": "changed",
    "data": [
      {
        "contractId": "90000002",
        "contractName": "ETHUSDT",
        "priceChange": "12.34",
        "priceChangePercent": "0.0052",
        "trades": "12345",
        "size": "456.789",
        "value": "1087654.32",
        "high": "2401.11",
        "low": "2333.22",
        "open": "2360.11",
        "close": "2379.95",
        "highTime": "1776220000000",
        "lowTime": "1776180000000",
        "startTime": "1776138900000",
        "endTime": "1776225300000",
        "lastPrice": "2379.95",
        "markPrice": "2379.95",
        "indexPrice": "2379.93",
        "openInterest": "0",
        "bestAskPrice": "2379.95",
        "bestBidPrice": "2379.93"
      }
    ]
  }
}
```

### Field Description

| Field | Description |
| --- | --- |
| `contractId` | Instrument ID returned as a string. |
| `contractName` | Instrument name. |
| `priceChange` | 24-hour price change. |
| `priceChangePercent` | 24-hour price change percent. |
| `trades` | 24-hour trade count. |
| `size` | 24-hour traded size. |
| `value` | 24-hour traded value. |
| `high` | 24-hour high price. |
| `low` | 24-hour low price. |
| `open` | 24-hour open price. |
| `close` | 24-hour close price. |
| `highTime` | Timestamp of the 24-hour high. |
| `lowTime` | Timestamp of the 24-hour low. |
| `startTime` | 24-hour window start time. |
| `endTime` | 24-hour window end time. |
| `lastPrice` | Latest traded price. |
| `markPrice` | Current mark price. |
| `indexPrice` | Current index price. |
| `openInterest` | Field retained by the model. |
| `bestAskPrice` | Best ask price. |
| `bestBidPrice` | Best bid price. |

### Aggregate Example

```json
{
  "type": "quote-event",
  "channel": "ticker.all.1s",
  "content": {
    "channel": "ticker.all.1s",
    "dataType": "changed",
    "data": []
  }
}
```

## Subscribe to Kline

### Channel Description

| Channel | Description |
| --- | --- |
| `kline.{priceType}.{instrumentId}.{interval}` | Subscribe to one instrument kline stream. |

### `priceType` Parameter

| Value | Description |
| --- | --- |
| `LAST_PRICE` | Last price kline. |
| `INDEX_PRICE` | Index price kline. |
| `MARK_PRICE` | Mark price kline. |

### `interval` Parameter

| Value | Description |
| --- | --- |
| `MINUTE_1` | 1-minute kline. |
| `MINUTE_5` | 5-minute kline. |
| `MINUTE_15` | 15-minute kline. |
| `MINUTE_30` | 30-minute kline. |
| `HOUR_1` | 1-hour kline. |
| `HOUR_2` | 2-hour kline. |
| `HOUR_4` | 4-hour kline. |
| `HOUR_6` | 6-hour kline. |
| `HOUR_8` | 8-hour kline. |
| `HOUR_12` | 12-hour kline. |
| `DAY_1` | 1-day kline. |
| `WEEK_1` | 1-week kline. |
| `MONTH_1` | 1-month kline. |

### Request

```json
{
  "type": "subscribe",
  "channel": "kline.LAST_PRICE.90000002.MINUTE_30"
}
```

### Response

```json
{
  "type": "subscribed",
  "channel": "kline.LAST_PRICE.90000002.MINUTE_30",
  "request": "{\"type\":\"subscribe\",\"channel\":\"kline.LAST_PRICE.90000002.MINUTE_30\"}"
}
```

### Payload

```json
{
  "type": "quote-event",
  "channel": "kline.LAST_PRICE.90000002.MINUTE_30",
  "content": {
    "channel": "kline.LAST_PRICE.90000002.MINUTE_30",
    "dataType": "Snapshot",
    "data": [
      {
        "klineId": "6184753048271959084",
        "contractId": "90000002",
        "klineType": "MINUTE_30",
        "klineTime": "1776171600000",
        "priceType": "LAST_PRICE",
        "trades": "636",
        "size": "509.334586",
        "value": "1212002.65924218",
        "high": "2382.35",
        "low": "2373.41",
        "open": "2374.92",
        "close": "2380.35",
        "makerBuySize": "509.334586",
        "makerBuyValue": "1212002.65924218"
      }
    ]
  }
}
```

### Field Description

| Field | Description |
| --- | --- |
| `klineId` | Kline ID. |
| `contractId` | Instrument ID returned as a string. |
| `contractName` | Instrument name when present. |
| `klineType` | Interval enum. |
| `klineTime` | Kline timestamp. |
| `priceType` | Price type enum. |
| `trades` | Trade count. |
| `size` | Traded size. |
| `value` | Traded value. |
| `high` | High price. |
| `low` | Low price. |
| `open` | Open price. |
| `close` | Close price. |
| `makerBuySize` | Maker buy size. |
| `makerBuyValue` | Maker buy value. |

## Subscribe to Depth

After a successful subscription, the gateway pushes a snapshot once and later pushes incremental updates when `depthType = CHANGED`.

### Channel Description

| Channel | Description |
| --- | --- |
| `depth.{instrumentId}.15` | Subscribe to the 15-level order book. |
| `depth.{instrumentId}.200` | Subscribe to the 200-level order book. |

### Request

```json
{
  "type": "subscribe",
  "channel": "depth.90000002.200"
}
```

### Response

```json
{
  "type": "subscribed",
  "channel": "depth.90000002.200",
  "request": "{\"type\":\"subscribe\",\"channel\":\"depth.90000002.200\"}"
}
```

### Payload

```json
{
  "type": "quote-event",
  "channel": "depth.90000002.200",
  "content": {
    "channel": "depth.90000002.200",
    "dataType": "Snapshot",
    "data": [
      {
        "startVersion": "111676529",
        "endVersion": "111676543",
        "level": 200,
        "contractId": "90000002",
        "asks": [
          {"price": "2379.95", "size": "3.621387"},
          {"price": "2379.96", "size": "1.599900"}
        ],
        "bids": [
          {"price": "2379.93", "size": "2.515200"},
          {"price": "2379.88", "size": "0.002567"}
        ],
        "depthType": "SNAPSHOT"
      }
    ]
  }
}
```

### Field Description

| Field | Description |
| --- | --- |
| `startVersion` | Start order book version. |
| `endVersion` | End order book version. |
| `level` | Subscribed depth level. |
| `contractId` | Instrument ID returned as a string. |
| `contractName` | Instrument name when present. |
| `asks` | Ask-side order book items. |
| `bids` | Bid-side order book items. |
| `depthType` | `SNAPSHOT` or `CHANGED`. |

Order item format:

| Field | Description |
| --- | --- |
| `price` | Price. |
| `size` | Size. |

## Subscribe to Latest Trades

### Channel Description

| Channel | Description |
| --- | --- |
| `trades.{instrumentId}` | Subscribe to the latest trades of one instrument. |

### Request

```json
{
  "type": "subscribe",
  "channel": "trades.90000002"
}
```

### Response

```json
{
  "type": "subscribed",
  "channel": "trades.90000002",
  "request": "{\"type\":\"subscribe\",\"channel\":\"trades.90000002\"}"
}
```

### Payload

```json
{
  "type": "quote-event",
  "channel": "trades.90000002",
  "content": {
    "channel": "trades.90000002",
    "dataType": "changed",
    "data": [
      {
        "ticketId": "1",
        "time": "1776225300000",
        "price": "2379.95",
        "size": "0.100000",
        "contractId": "90000002",
        "isBuyerMaker": false
      }
    ]
  }
}
```

### Field Description

| Field | Description |
| --- | --- |
| `ticketId` | Trade ID. |
| `time` | Trade timestamp. |
| `price` | Trade price. |
| `size` | Trade size. |
| `contractId` | Instrument ID returned as a string. |
| `isBuyerMaker` | Trade side marker. |
