# websocket接口

## (Private WebSocket) 用户账户信息websocket接口

### 说明

> + 01. Private WebSocket 不用订阅，连接之后自动推送数据。包含交易消息和自定义消息。
> + 02. 交易消息的type规定为`type-event`；其他消息另行定义
> + 03. 交易消息的消息体中的`event`包括 `Snapshot`/`ACCOUNT_UPDATE`/`DEPOSIT_UPDATE`/`WITHDRAW_UPDATE`/`TRANSFER_IN_UPDATE`/`TRANSFER_OUT_UPDATE`/`ORDER_UPDATE`/`FORCE_WITHDRAW_UPDATE`/`FORCE_TRADE_UPDATE`/`FUNDING_SETTLEMENT`/`ORDER_FILL_FEE_INCOME`/`START_LIQUIDATING`/`FINISH_LIQUIDATING`/`UNRECOGNIZED`
> + 04. Ping-Pong机制
> > - 服务端 `Ping`(用于心跳)
> > > WebSocket连接成功之后，Server端会以固定频率向Client端发送Ping消息，消息体如下：`{"type":"ping","time":"1693208170000"}`
，其中time标示的是Server端Ping时刻的时间戳。此时Client端在收到消息后，请回复服务端Pong消息，消息体内容为 `{"type":"pong","time":"1693208170000"}`
。超过5次不回应，服务端会主动断开当前连接。
> > - 客户端 `Ping`(用于测速)
> > > WebSocket连接成功后，Client端也可以自己发起一个Ping消息，消息体如下：`{"type":"ping","time":"1693208170000"}`
> > > ，其中time为Client端发起Ping消息的时间戳，照此消息格式，服务端在收到消息之后，会即刻回复Pong消息，消息体内容为 `{"type":"pong","time":"1693208170000"}`
> > > ，其中的`time`字段还是Client端Ping消息的`time`。
> + 05. 鉴权
> > - WEB
> > > + 由于浏览器不允许在WebSocket链接时候使用自定义Header，所以需要特殊处理一下。
> > > + 使用和Http一样的鉴权逻辑，把本该放在Header中的`X-Edgex-Api-Key`/`X-Edgex-Passphrase`/`X-Edgex-Signature`/`X-Edgex-Timestamp`中的四个Key和Value组成一个json字符串`{"X-Edgex-Api-Key": "ff072a89-78a9-b4e8-27b2-32bd774c0786", "X-Edgex-Passphrase": "BEomwWBDjPqj7yifePhY2Q", "X-Edgex-Signature": "69ce1a38fd65afc49ae81eaccca81bfddb6a73cb3936b7d53abf48003514c253", "X-Edgex-Timestamp": "1705720068228"}`
> > > + 对json字符串做一次 base64 编码
> > > + WebSocket请求的时候，使用 Header: `SEC_WEBSOCKET_PROTOCOL`将base64编码后的值传递到服务端即可
> > - APP
> > > APP的WebSocket链接可以自定义Header，所以APP可以继续使用和HTTP一样的鉴权逻辑，或者也可以使用上面描述的Web的WebSocket鉴权逻辑

### URL: `/api/v1/private/ws`

#### payload

```json5
{
  // 交易消息的type为type-event，自定义消息的type单独定义，error表示是服务端推送的错误消息
  "type": "trade-event",
  // 交易消息的消息体结构如下。自定义消息的消息结构体由使用方单独定义
  "content": {
    // 引起数据变更的事件
    "event": "ACCOUNT_UPDATE",
    // 数据变更version
    "version": "1000",
    // 数据
    "data": {
      // 账户信息
      "account": [
      ],
      // 抵押品
      "collateral": [
      ],
      // 抵押品变动明细
      "collateralTransaction": [
      ],
      // 持仓信息
      "position": [
      ],
      // 持仓变动明细
      "positionTransaction": [
      ],
      // 充值单
      "deposit": [
      ],
      // 提现单
      "withdraw": [
      ],
      // 转入单
      "transferIn": [
      ],
      // 转出单
      "transferOut": [
      ],
      // 委托单
      "order": [
      ],
      // 成交明细
      "orderFillTransaction": [
      ]
    }
  }
}
```

## (Public WebSocket)行情websocket接口

### URL: ``/api/v1/public/ws``

### 说明

> + 01. 订阅和取消订阅，服务端都会校验channel，对于不合法的channel，服务端会响应error消息，例如： `{"type":"error","content":{"code":"INVALID_CONTRACT_ID""msg":"invalid contractId:100000001"}}`
> + 02. 消息的订阅和取消订阅结构体: {"type": "subscribe", "channel": "ticker.10000001"}.
> + 03. Ping-Pong机制
> > - 服务端 `Ping`(用于心跳)
> > > WebSocket连接成功之后，Server端会以固定频率向Client端发送Ping消息，消息体如下：`{"type":"ping","time":"1693208170000"}`
，其中time标示的是Server端Ping时刻的时间戳。此时Client端在收到消息后，请回复服务端Pong消息，消息体内容为 `{"type":"pong","time":"1693208170000"}`
。超过5次不回应，服务端会主动断开当前连接。
> > - 客户端 `Ping`(用于测速)
> > > WebSocket连接成功后，Client端也可以自己发起一个Ping消息，消息体如下：`{"type":"ping","time":"1693208170000"}`
> > > ，其中time为Client端发起Ping消息的时间戳，照此消息格式，服务端在收到消息之后，会即刻回复Pong消息，消息体内容为 `{"type":"pong","time":"1693208170000"}`
> > > ，其中的`time`字段还是Client端Ping消息的`time`。

### 订阅metadata

#### request

```json5
{
  "type": "subscribe",
  "channel": "metadata"
}
```

#### response

```json5
{
  "type": "subscribed",
  "channel": "metadata"
}
```

#### payload

```json lines
{
  // error
  "type":  "quote-event",
  "channel": "metadata",
  "content": {
    // snapshot quote-event 
    "dataType": "Snapshot", 
    // 
    "channel": "metadata",
    "data": [
      {
        // 币信息
        "coin": [
        ],
        // 合约信息
        "contract": [
        ]
      }
    ]
  }
}
```

### 订阅24小时行情

#### channel说明

| channel             | 备注                  |
|---------------------|---------------------|
| ticker.{contractId} | 订阅合约contractId的行情信息 |
| ticker.all          | 订阅所有合约的行情信息         |
| ticker.all.1s       | 订阅所有合约的行情信息 (定时推送)  |

#### request

```json5
{
  "type": "subscribe",
  "channel": "ticker.10000001"
}
```

#### response

```json5
{
  "type": "subscribed",
  "channel": "ticker.10000001"
}
```

#### payload

```json lines
{
  "type": "payload",
  "channel": "ticker.10000001",
  "content": {
    "dataType": "Snapshot",
    "channel": "ticker.10000001",
    "data": [
      {
        "contractId": "string",
        "priceChange": "string",
        "priceChangePercent": "string",
        "trades": "string",
        "size": "string",
        "value": "string",
        "high": "string",
        "low": "string",
        "open": "string",
        "close": "string",
        "highTime": "string",
        "lowTime": "string",
        "startTime": "string",
        "endTime": "string",
        "lastPrice": "string",
      }
    ]
  },
}
```

### 订阅K线

#### channel说明

| channel                                   | 备注                                        |
|-------------------------------------------|-------------------------------------------|
| kline.{priceType}.{contractId}.{interval} | 订阅合约contractId的价格类型为priceType的interval K线 |

#### priceType 参数

> | value      | description |
> |------------|-------------|
> | LAST_PRICE | 最新价格K线      |
> | MARK_PRICE | 标价价格K线      |

#### interval 参数

> | value     | description |
> |:----------|-------------|
> | MINUTE_1  | 1分钟线        |
> | MINUTE_5  | 5分钟线        |
> | MINUTE_15 | 15分钟线       |
> | MINUTE_30 | 30分钟线       |
> | HOUR_1    | 1小时线        |
> | HOUR_2    | 2小时线        |
> | HOUR_4    | 4小时线        |
> | HOUR_6    | 6小时线        |
> | HOUR_8    | 8小时线        |
> | HOUR_12   | 12小时线       |
> | DAY_1     | 天线          |
> | WEEK_1    | 周线          |
> | MONTH_1   | 月线          |

#### request

```json5
{
  "type": "subscribe",
  "channel": "kline.LAST_PRICE.10000001.MINUTE_1"
}
```

#### response

```json5
{
  "type": "subscribed",
  "channel": "kline.LAST_PRICE.10000001.MINUTE_1"
}
```

#### payload

```json5
{
  "type": "payload",
  "channel": "kline.LAST_PRICE.10000001.MINUTE_1",
  "content": {
    "dataType": "Changed",
    "channel": "kline.LAST_PRICE.10000001.MINUTE_1",
    "data": [
      {
        "klineId": "1",
        "contractId": "10000001",
        "klineType": "MINUTE_1",
        "klineTime": "1688365544504",
        "trades": "5",
        "size": "10.1",
        "value": "100000",
        "high": "31200",
        "low": "31000",
        "open": "3150",
        "close": "31010",
        "makerBuySize": "5",
        "makerBuyValue": "150000"
      }
    ]
  },
}
```

### 订阅订单薄

#### 使用说明

> 订阅成功后，会直接推送一次全量数据(depthType=SNAPSHOT)，后续推送为增量数据(depthType=CHANGED)

#### channel说明

| channel                    | 备注                          |
|----------------------------|-----------------------------|
| depth.{contractId}.{depth} | 订阅合约contractId的深度为depth的订单簿 |

#### depth 参数

> | value | description |
> |-------|-------------|
> | 15    | 15档         |
> | 200   | 200档        |

#### request

```json5
{
  "type": "subscribe",
  "channel": "depth.10000001.15"
}
```

#### response

```json5
{
  "type": "subscribed",
  "channel": "depth.10000001.15"
}
```

#### payload

```json5
{
  "type": "payload",
  "channel": "depth.10000001.15",
  "content": {
    "dataType": "Snapshot",
    "channel": "depth.10000001.15",
    "data": [
      {
        "startVersion": "string",
        "endVersion": "string",
        "level": 0,
        "contractId": "10000001",
        "depthType": "Snapshot",
        // 数据类型 SNAPSHOT 全量数据 SNAPSHOT 增量数据
        "bids": [
          [
            "26092",
            // 价格
            "0.9014"
            // 数量 数量为0表示删除该价格 正数表示增加 负数表示减少
          ],
          [
            "26091",
            "0.9667"
          ]
        ],
        "asks": [
          [
            "26093",
            "0.964"
          ],
          [
            "26094",
            "1.0213"
          ]
        ]
      }
    ]
  }
}
```

### 订阅最新成交

#### channel说明

| channel             | 备注                  |
|---------------------|---------------------|
| trades.{contractId} | 订阅合约contractId的最新成交 |

#### request

```json5
{
  "type": "subscribe",
  "channel": "trades.10000001"
}
```

#### response

```json5
{
  "type": "subscribed",
  "channel": "trades.10000001"
}
```

#### payload

```json5
{
  "type": "payload",
  "channel": "trades.10000001",
  "content": {
    "dataType": "Changed",
    "channel": "trades.10000001",
    "data": [
      {
        "ticketId": "1",
        "time": "1688365544504",
        "price": "30065.12",
        "size": "0.01",
        "value": "300.6512",
        "takerOrderId": "10",
        "makerOrderId": "11",
        "takerAccountId": "3001",
        "makerAccountId": "3002",
        "contractId": "10000001",
        "isBestMatch": true,
        "isBuyerMaker": false
      }
    ]
  }
}
```

