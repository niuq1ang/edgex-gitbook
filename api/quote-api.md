---
title: test v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.17"

---

# test

> v1.0.0

Base URLs:

# 01.QuotePublicApi

<a id="opIdgetTicketSummary"></a>

## GET 获取行情汇总

GET /api/v1/public/quote/getTicketSummary

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|period|query|string| 否 |汇总周期|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdgetTicker"></a>

## GET 查询24小时行情

GET /api/v1/public/quote/getTicker

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractId|query|string| 否 |合约id|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "contractName": "string",
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
      "indexPrice": "string",
      "oraclePrice": "string",
      "openInterest": "string",
      "fundingRate": "string",
      "fundingTime": "string",
      "nextFundingTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetStatDayTrade"></a>

## GET 获取日交易统计

GET /api/v1/public/quote/getStatDayTrade

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|startDayTimeInclusive|query|string| 否 |过滤获取指定开始时间的交易统计信息|
|endDayTimeExclusive|query|string| 否 | 过滤获取指定结束时间的日交易统计信息|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdgetMultiContractKline"></a>

## GET 查询多合约定量K线

GET /api/v1/public/quote/getMultiContractKline

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractIdList|query|string| 否 |合约id集合|
|priceType|query|string| 否 |价格类型|
|klineType|query|string| 否 |K线类型|
|size|query|string| 否 |获取数量。必须大于0且小于等于200|
|filterBeginKlineTimeInclusive|query|string| 否 |查询开始时间（如果为0表示从当前时间）按照时间倒序向前查询返回|
|filterEndKlineTimeExclusive|query|string| 否 |查询结束时间|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "klineList": [
        {
          "klineId": "string",
          "contractId": "string",
          "contractName": "string",
          "klineType": "UNKNOWN_KLINE_TYPE",
          "klineTime": "string",
          "priceType": "UNKNOWN_PRICE_TYPE",
          "trades": "string",
          "size": "string",
          "value": "string",
          "high": "string",
          "low": "string",
          "open": "string",
          "close": "string",
          "makerBuySize": "string",
          "makerBuyValue": "string"
        }
      ]
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetKline"></a>

## GET 查询K线

GET /api/v1/public/quote/getKline

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractId|query|string| 否 |合约id|
|priceType|query|string| 否 |价格类型|
|klineType|query|string| 否 |K线类型|
|size|query|string| 否 |获取数量。必须大于0且小于等于1000|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterBeginKlineTimeInclusive|query|string| 否 |查询开始时间（如果为0表示从当前时间）按照时间倒序向前查询返回|
|filterEndKlineTimeExclusive|query|string| 否 |查询结束时间|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdgetExchangeLongShortRatio"></a>

## GET 获取日交易统计

GET /api/v1/public/quote/getExchangeLongShortRatio

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|range|query|string| 否 |如果为空的话，默认返回 range 最小的数据|
|filterContractIdList|query|string| 否 |如果为空的话，默认返回所有合约数据|
|filterExchangeList|query|string| 否 |如果为空的话，默认返回所有交易所数据|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdgetDepth"></a>

## GET 查询盘口深度

GET /api/v1/public/quote/getDepth

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractId|query|string| 否 |合约id|
|level|query|string| 否 |深度档位 目前有15档和200档|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "startVersion": "string",
      "endVersion": "string",
      "level": 0,
      "contractId": "string",
      "contractName": "string",
      "asks": [
        {
          "price": "string",
          "size": "string"
        }
      ],
      "bids": [
        {
          "price": "string",
          "size": "string"
        }
      ],
      "depthType": "UNKNOWN_DEPTH_TYPE"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetAccurateOpenInterest"></a>

## GET 获取精确OpenInterest

GET /api/v1/public/quote/getAccurateOpenInterest

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractIdList|query|string| 否 |合约id集合|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

# 数据模型

<h2 id="tocS_Result<List<OpenInterest>>">Result<List<OpenInterest>></h2>

<a id="schemaresult<list<openinterest>>"></a>
<a id="schema_Result<List<OpenInterest>>"></a>
<a id="tocSresult<list<openinterest>>"></a>
<a id="tocsresult<list<openinterest>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "timestamp": "string",
      "size": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[OpenInterest](#schemaopeninterest)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_OpenInterest">OpenInterest</h2>

<a id="schemaopeninterest"></a>
<a id="schema_OpenInterest"></a>
<a id="tocSopeninterest"></a>
<a id="tocsopeninterest"></a>

```json
{
  "contractId": "string",
  "timestamp": "string",
  "size": "string"
}

```

持仓量

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约ID|
|timestamp|string|false|none||统计时间戳|
|size|string(int64)|false|none||持仓量|

<h2 id="tocS_Result<List<Depth>>">Result<List<Depth>></h2>

<a id="schemaresult<list<depth>>"></a>
<a id="schema_Result<List<Depth>>"></a>
<a id="tocSresult<list<depth>>"></a>
<a id="tocsresult<list<depth>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "startVersion": "string",
      "endVersion": "string",
      "level": 0,
      "contractId": "string",
      "contractName": "string",
      "asks": [
        {
          "price": "string",
          "size": "string"
        }
      ],
      "bids": [
        {
          "price": "string",
          "size": "string"
        }
      ],
      "depthType": "UNKNOWN_DEPTH_TYPE"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[Depth](#schemadepth)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Depth">Depth</h2>

<a id="schemadepth"></a>
<a id="schema_Depth"></a>
<a id="tocSdepth"></a>
<a id="tocsdepth"></a>

```json
{
  "startVersion": "string",
  "endVersion": "string",
  "level": 0,
  "contractId": "string",
  "contractName": "string",
  "asks": [
    {
      "price": "string",
      "size": "string"
    }
  ],
  "bids": [
    {
      "price": "string",
      "size": "string"
    }
  ],
  "depthType": "UNKNOWN_DEPTH_TYPE"
}

```

深度

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|startVersion|string(int64)|false|none||开始订单簿版本号|
|endVersion|string(int64)|false|none||结束订单簿版本号|
|level|integer(int32)|false|none||深度档位|
|contractId|string(int64)|false|none||合约id|
|contractName|string|false|none||合约名称|
|asks|[[BookOrder](#schemabookorder)]|false|none||ask列表|
|bids|[[BookOrder](#schemabookorder)]|false|none||bid列表|
|depthType|string|false|none||盘口深度类型|

#### 枚举值

|属性|值|
|---|---|
|depthType|UNKNOWN_DEPTH_TYPE|
|depthType|SNAPSHOT|
|depthType|CHANGED|
|depthType|UNRECOGNIZED|

<h2 id="tocS_BookOrder">BookOrder</h2>

<a id="schemabookorder"></a>
<a id="schema_BookOrder"></a>
<a id="tocSbookorder"></a>
<a id="tocsbookorder"></a>

```json
{
  "price": "string",
  "size": "string"
}

```

订单簿信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|price|string(decimal)|false|none||价格|
|size|string(decimal)|false|none||数量|

<h2 id="tocS_Result<PageData<Kline>>">Result<PageData<Kline>></h2>

<a id="schemaresult<pagedata<kline>>"></a>
<a id="schema_Result<PageData<Kline>>"></a>
<a id="tocSresult<pagedata<kline>>"></a>
<a id="tocsresult<pagedata<kline>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "klineId": "string",
        "contractId": "string",
        "contractName": "string",
        "klineType": "UNKNOWN_KLINE_TYPE",
        "klineTime": "string",
        "priceType": "UNKNOWN_PRICE_TYPE",
        "trades": "string",
        "size": "string",
        "value": "string",
        "high": "string",
        "low": "string",
        "open": "string",
        "close": "string",
        "makerBuySize": "string",
        "makerBuyValue": "string"
      }
    ],
    "nextPageOffsetData": "string"
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[PageDataKline](#schemapagedatakline)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataKline">PageDataKline</h2>

<a id="schemapagedatakline"></a>
<a id="schema_PageDataKline"></a>
<a id="tocSpagedatakline"></a>
<a id="tocspagedatakline"></a>

```json
{
  "dataList": [
    {
      "klineId": "string",
      "contractId": "string",
      "contractName": "string",
      "klineType": "UNKNOWN_KLINE_TYPE",
      "klineTime": "string",
      "priceType": "UNKNOWN_PRICE_TYPE",
      "trades": "string",
      "size": "string",
      "value": "string",
      "high": "string",
      "low": "string",
      "open": "string",
      "close": "string",
      "makerBuySize": "string",
      "makerBuyValue": "string"
    }
  ],
  "nextPageOffsetData": "string"
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[Kline](#schemakline)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Kline">Kline</h2>

<a id="schemakline"></a>
<a id="schema_Kline"></a>
<a id="tocSkline"></a>
<a id="tocskline"></a>

```json
{
  "klineId": "string",
  "contractId": "string",
  "contractName": "string",
  "klineType": "UNKNOWN_KLINE_TYPE",
  "klineTime": "string",
  "priceType": "UNKNOWN_PRICE_TYPE",
  "trades": "string",
  "size": "string",
  "value": "string",
  "high": "string",
  "low": "string",
  "open": "string",
  "close": "string",
  "makerBuySize": "string",
  "makerBuyValue": "string"
}

```

K线

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|klineId|string(int64)|false|none||K线ID|
|contractId|string(int64)|false|none||永续合约id|
|contractName|string|false|none||永续合约名称|
|klineType|string|false|none||K线类型|
|klineTime|string(int64)|false|none||K线时间|
|priceType|string|false|none||K线的价格类型|
|trades|string(int64)|false|none||成交笔数|
|size|string(decimal)|false|none||成交量|
|value|string(decimal)|false|none||成交额|
|high|string(decimal)|false|none||最高价|
|low|string(decimal)|false|none||最低价|
|open|string(decimal)|false|none||内开盘价|
|close|string(decimal)|false|none||内收盘价|
|makerBuySize|string(decimal)|false|none||Maker买入成交量|
|makerBuyValue|string(decimal)|false|none||Maker买入成交额|

#### 枚举值

|属性|值|
|---|---|
|klineType|UNKNOWN_KLINE_TYPE|
|klineType|MINUTE_1|
|klineType|MINUTE_5|
|klineType|MINUTE_15|
|klineType|MINUTE_30|
|klineType|HOUR_1|
|klineType|HOUR_2|
|klineType|HOUR_4|
|klineType|HOUR_6|
|klineType|HOUR_8|
|klineType|HOUR_12|
|klineType|DAY_1|
|klineType|WEEK_1|
|klineType|MONTH_1|
|klineType|UNRECOGNIZED|
|priceType|UNKNOWN_PRICE_TYPE|
|priceType|ORACLE_PRICE|
|priceType|INDEX_PRICE|
|priceType|LAST_PRICE|
|priceType|ASK1_PRICE|
|priceType|BID1_PRICE|
|priceType|OPEN_INTEREST|
|priceType|UNRECOGNIZED|

<h2 id="tocS_Result<List<ContractKline>>">Result<List<ContractKline>></h2>

<a id="schemaresult<list<contractkline>>"></a>
<a id="schema_Result<List<ContractKline>>"></a>
<a id="tocSresult<list<contractkline>>"></a>
<a id="tocsresult<list<contractkline>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "klineList": [
        {
          "klineId": "string",
          "contractId": "string",
          "contractName": "string",
          "klineType": "UNKNOWN_KLINE_TYPE",
          "klineTime": "string",
          "priceType": "UNKNOWN_PRICE_TYPE",
          "trades": "string",
          "size": "string",
          "value": "string",
          "high": "string",
          "low": "string",
          "open": "string",
          "close": "string",
          "makerBuySize": "string",
          "makerBuyValue": "string"
        }
      ]
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[ContractMultiKline](#schemacontractmultikline)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_ContractMultiKline">ContractMultiKline</h2>

<a id="schemacontractmultikline"></a>
<a id="schema_ContractMultiKline"></a>
<a id="tocScontractmultikline"></a>
<a id="tocscontractmultikline"></a>

```json
{
  "contractId": "string",
  "klineList": [
    {
      "klineId": "string",
      "contractId": "string",
      "contractName": "string",
      "klineType": "UNKNOWN_KLINE_TYPE",
      "klineTime": "string",
      "priceType": "UNKNOWN_PRICE_TYPE",
      "trades": "string",
      "size": "string",
      "value": "string",
      "high": "string",
      "low": "string",
      "open": "string",
      "close": "string",
      "makerBuySize": "string",
      "makerBuyValue": "string"
    }
  ]
}

```

合约多条K线

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||永续合约id|
|klineList|[[Kline](#schemakline)]|false|none||kline数据集合|

<h2 id="tocS_Result<List<StatDayTrade>>">Result<List<StatDayTrade>></h2>

<a id="schemaresult<list<statdaytrade>>"></a>
<a id="schema_Result<List<StatDayTrade>>"></a>
<a id="tocSresult<list<statdaytrade>>"></a>
<a id="tocsresult<list<statdaytrade>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "dayTime": "string",
      "totalTrades": "string",
      "totalValue": "string",
      "createTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[StatDayTrade](#schemastatdaytrade)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_StatDayTrade">StatDayTrade</h2>

<a id="schemastatdaytrade"></a>
<a id="schema_StatDayTrade"></a>
<a id="tocSstatdaytrade"></a>
<a id="tocsstatdaytrade"></a>

```json
{
  "dayTime": "string",
  "totalTrades": "string",
  "totalValue": "string",
  "createTime": "string"
}

```

日交易信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dayTime|string(int64)|false|none||日期|
|totalTrades|string(int64)|false|none||总交易笔数|
|totalValue|string|false|none||总交易额|
|createTime|string(int64)|false|none||创建时间|

<h2 id="tocS_Result<List<Ticker>>">Result<List<Ticker>></h2>

<a id="schemaresult<list<ticker>>"></a>
<a id="schema_Result<List<Ticker>>"></a>
<a id="tocSresult<list<ticker>>"></a>
<a id="tocsresult<list<ticker>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "contractName": "string",
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
      "indexPrice": "string",
      "oraclePrice": "string",
      "openInterest": "string",
      "fundingRate": "string",
      "fundingTime": "string",
      "nextFundingTime": "string"
    }
  ],
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[Ticker](#schematicker)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Ticker">Ticker</h2>

<a id="schematicker"></a>
<a id="schema_Ticker"></a>
<a id="tocSticker"></a>
<a id="tocsticker"></a>

```json
{
  "contractId": "string",
  "contractName": "string",
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
  "indexPrice": "string",
  "oraclePrice": "string",
  "openInterest": "string",
  "fundingRate": "string",
  "fundingTime": "string",
  "nextFundingTime": "string"
}

```

24小时行情

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约ID|
|contractName|string|false|none||合约名称|
|priceChange|string(decimal)|false|none||价格涨跌幅|
|priceChangePercent|string(decimal)|false|none||价格涨跌幅百分比|
|trades|string(int64)|false|none||24小时成交笔数|
|size|string(decimal)|false|none||24小时成交量|
|value|string(decimal)|false|none||24小时成交额|
|high|string(decimal)|false|none||24小时最高价|
|low|string(decimal)|false|none||24小时最低价|
|open|string(decimal)|false|none||24小时内开盘价|
|close|string(decimal)|false|none||24小时内收盘价|
|highTime|string(int64)|false|none||24小时最高价时间|
|lowTime|string(int64)|false|none||24小时最低价时间|
|startTime|string(int64)|false|none||24小时行情开始时间|
|endTime|string(int64)|false|none||24小时行情结束时间|
|lastPrice|string(decimal)|false|none||最新成交价|
|indexPrice|string(decimal)|false|none||当前指数价格|
|oraclePrice|string(decimal)|false|none||当前预言机价格|
|openInterest|string(decimal)|false|none||未平仓持仓量|
|fundingRate|string|false|none||当前已经结算的资金费率|
|fundingTime|string(int64)|false|none||资金费率结算时间|
|nextFundingTime|string(int64)|false|none||下次资金费率结算时间|

<h2 id="tocS_Result<GetTickerSummaryModel>">Result<GetTickerSummaryModel></h2>

<a id="schemaresult<gettickersummarymodel>"></a>
<a id="schema_Result<GetTickerSummaryModel>"></a>
<a id="tocSresult<gettickersummarymodel>"></a>
<a id="tocsresult<gettickersummarymodel>"></a>

```json
{
  "code": "string",
  "data": {
    "tickerSummary": {
      "period": "UNKNOWN_PERIOD",
      "trades": "string",
      "value": "string",
      "openInterest": "string"
    }
  },
  "errorParam": {
    "property1": "string",
    "property2": "string"
  },
  "requestTime": "string",
  "responseTime": "string",
  "traceId": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[GetTickerSummary](#schemagettickersummary)|false|none||获取行情汇总响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetTickerSummary">GetTickerSummary</h2>

<a id="schemagettickersummary"></a>
<a id="schema_GetTickerSummary"></a>
<a id="tocSgettickersummary"></a>
<a id="tocsgettickersummary"></a>

```json
{
  "tickerSummary": {
    "period": "UNKNOWN_PERIOD",
    "trades": "string",
    "value": "string",
    "openInterest": "string"
  }
}

```

获取行情汇总响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|tickerSummary|[TickerSummary](#schematickersummary)|false|none||行情汇总|

<h2 id="tocS_TickerSummary">TickerSummary</h2>

<a id="schematickersummary"></a>
<a id="schema_TickerSummary"></a>
<a id="tocStickersummary"></a>
<a id="tocstickersummary"></a>

```json
{
  "period": "UNKNOWN_PERIOD",
  "trades": "string",
  "value": "string",
  "openInterest": "string"
}

```

行情汇总

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|period|string|false|none||汇总周期|
|trades|string|false|none||交易所总交易笔数|
|value|string|false|none||总成交金额|
|openInterest|string|false|none||当前总未平仓额|

#### 枚举值

|属性|值|
|---|---|
|period|UNKNOWN_PERIOD|
|period|LAST_DAY_1|
|period|LAST_DAY_7|
|period|LAST_DAY_30|
|period|UNRECOGNIZED|

<h2 id="tocS_Result">Result</h2>

<a id="schemaresult"></a>
<a id="schema_Result"></a>
<a id="tocSresult"></a>
<a id="tocsresult"></a>

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}

```

通用返回结构体

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|msg|string|false|none||当发生错误时的详细错误信息|
|requestTime|string(int64)|false|none||服务器请求接收时间|
|responseTime|string(int64)|false|none||服务器响应返回时间|

