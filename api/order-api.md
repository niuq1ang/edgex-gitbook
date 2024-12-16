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

# 04.OrderPrivateApi

<a id="opIdgetMaxCreateOrderSize"></a>

## POST 获取最大下单数量

POST /api/v1/private/order/getMaxCreateOrderSize

> Body 请求参数

```json
{
  "accountId": "string",
  "contractId": "string",
  "price": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[GetMaxCreateOrderSizeParam](#schemagetmaxcreateordersizeparam)| 否 |none|

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

<a id="opIdcreateOrder"></a>

## POST 创建委托单

POST /api/v1/private/order/createOrder

> Body 请求参数

```json
{
  "accountId": "string",
  "contractId": "string",
  "side": "UNKNOWN_ORDER_SIDE",
  "size": "string",
  "price": "string",
  "clientOrderId": "string",
  "type": "UNKNOWN_ORDER_TYPE",
  "timeInForce": "UNKNOWN_TIME_IN_FORCE",
  "reduceOnly": true,
  "triggerPrice": "string",
  "triggerPriceType": "UNKNOWN_PRICE_TYPE",
  "expireTime": "string",
  "sourceKey": "string",
  "isPositionTpsl": true,
  "openTpslParentOrderId": "string",
  "isSetOpenTp": true,
  "openTp": {
    "side": "UNKNOWN_ORDER_SIDE",
    "price": "string",
    "size": "string",
    "clientOrderId": "string",
    "triggerPrice": "string",
    "triggerPriceType": "UNKNOWN_PRICE_TYPE",
    "expireTime": "string",
    "l2Nonce": "string",
    "l2Value": "string",
    "l2Size": "string",
    "l2LimitFee": "string",
    "l2ExpireTime": "string",
    "l2Signature": "string"
  },
  "isSetOpenSl": true,
  "openSl": {
    "side": "UNKNOWN_ORDER_SIDE",
    "price": "string",
    "size": "string",
    "clientOrderId": "string",
    "triggerPrice": "string",
    "triggerPriceType": "UNKNOWN_PRICE_TYPE",
    "expireTime": "string",
    "l2Nonce": "string",
    "l2Value": "string",
    "l2Size": "string",
    "l2LimitFee": "string",
    "l2ExpireTime": "string",
    "l2Signature": "string"
  },
  "l2Nonce": "string",
  "l2Value": "string",
  "l2Size": "string",
  "l2LimitFee": "string",
  "l2ExpireTime": "string",
  "l2Signature": "string",
  "extraType": "string",
  "extraDataJson": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateOrderParam](#schemacreateorderparam)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {
    "orderId": "string"
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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdcancelOrderById"></a>

## POST 根据委托单id取消委托单

POST /api/v1/private/order/cancelOrderById

> Body 请求参数

```json
{
  "accountId": "string",
  "orderIdList": [
    "string"
  ]
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CancelOrderByIdParam](#schemacancelorderbyidparam)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {
    "cancelResultMap": {
      "property1": "UNKNOWN_ORDER_CANCEL_RESULT",
      "property2": "UNKNOWN_ORDER_CANCEL_RESULT"
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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdcancelOrderByClientOrderId"></a>

## POST 根据clientId取消委托单

POST /api/v1/private/order/cancelOrderByClientOrderId

> Body 请求参数

```json
{
  "accountId": "string",
  "clientOrderIdList": [
    "string"
  ]
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CancelOrderByClientOrderIdParam](#schemacancelorderbyclientorderidparam)| 否 |none|

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

<a id="opIdcancelAllOrder"></a>

## POST 取消账户下所有委托单

POST /api/v1/private/order/cancelAllOrder

> Body 请求参数

```json
{
  "accountId": "string",
  "filterCoinIdList": [
    "string"
  ],
  "filterContractIdList": [
    "string"
  ],
  "filterOrderTypeList": [
    "UNKNOWN_ORDER_TYPE"
  ],
  "filterOrderStatusList": [
    "UNKNOWN_ORDER_STATUS"
  ],
  "filterIsPositionTpsl": [
    true
  ]
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CancelAllOrderParam](#schemacancelallorderparam)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {
    "cancelResultMap": {
      "property1": "UNKNOWN_ORDER_CANCEL_RESULT",
      "property2": "UNKNOWN_ORDER_CANCEL_RESULT"
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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetOrderById"></a>

## GET 根据账户id和委托单id批量获取委托单

GET /api/v1/private/order/getOrderById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|orderIdList|query|string| 否 |委托单id|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "side": "UNKNOWN_ORDER_SIDE",
      "price": "string",
      "size": "string",
      "clientOrderId": "string",
      "type": "UNKNOWN_ORDER_TYPE",
      "timeInForce": "UNKNOWN_TIME_IN_FORCE",
      "reduceOnly": true,
      "triggerPrice": "string",
      "triggerPriceType": "UNKNOWN_PRICE_TYPE",
      "expireTime": "string",
      "sourceKey": "string",
      "isPositionTpsl": true,
      "isLiquidate": true,
      "isDeleverage": true,
      "openTpslParentOrderId": "string",
      "isSetOpenTp": true,
      "openTp": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isSetOpenSl": true,
      "openSl": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isWithoutMatch": true,
      "withoutMatchFillSize": "string",
      "withoutMatchFillValue": "string",
      "withoutMatchPeerAccountId": "string",
      "withoutMatchPeerOrderId": "string",
      "maxLeverage": "string",
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "liquidateFeeRate": "string",
      "marketLimitPrice": "string",
      "marketLimitValue": "string",
      "l2Nonce": "string",
      "l2Value": "string",
      "l2Size": "string",
      "l2LimitFee": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ORDER_STATUS",
      "matchSequenceId": "string",
      "triggerTime": "string",
      "triggerPriceTime": "string",
      "triggerPriceValue": "string",
      "cancelReason": "UNKNOWN_ORDER_CANCEL_REASON",
      "cumFillSize": "string",
      "cumFillValue": "string",
      "cumFillFee": "string",
      "maxFillPrice": "string",
      "minFillPrice": "string",
      "cumLiquidateFee": "string",
      "cumRealizePnl": "string",
      "cumMatchSize": "string",
      "cumMatchValue": "string",
      "cumMatchFee": "string",
      "cumFailSize": "string",
      "cumFailValue": "string",
      "cumFailFee": "string",
      "cumApprovedSize": "string",
      "cumApprovedValue": "string",
      "cumApprovedFee": "string",
      "createdTime": "string",
      "updatedTime": "string"
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

<a id="opIdgetOrderByClientOrderId"></a>

## GET 根据客户id批量获取委托单

GET /api/v1/private/order/getOrderByClientOrderId

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|clientOrderIdList|query|string| 否 |客户端自定义委托单id|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "side": "UNKNOWN_ORDER_SIDE",
      "price": "string",
      "size": "string",
      "clientOrderId": "string",
      "type": "UNKNOWN_ORDER_TYPE",
      "timeInForce": "UNKNOWN_TIME_IN_FORCE",
      "reduceOnly": true,
      "triggerPrice": "string",
      "triggerPriceType": "UNKNOWN_PRICE_TYPE",
      "expireTime": "string",
      "sourceKey": "string",
      "isPositionTpsl": true,
      "isLiquidate": true,
      "isDeleverage": true,
      "openTpslParentOrderId": "string",
      "isSetOpenTp": true,
      "openTp": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isSetOpenSl": true,
      "openSl": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isWithoutMatch": true,
      "withoutMatchFillSize": "string",
      "withoutMatchFillValue": "string",
      "withoutMatchPeerAccountId": "string",
      "withoutMatchPeerOrderId": "string",
      "maxLeverage": "string",
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "liquidateFeeRate": "string",
      "marketLimitPrice": "string",
      "marketLimitValue": "string",
      "l2Nonce": "string",
      "l2Value": "string",
      "l2Size": "string",
      "l2LimitFee": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ORDER_STATUS",
      "matchSequenceId": "string",
      "triggerTime": "string",
      "triggerPriceTime": "string",
      "triggerPriceValue": "string",
      "cancelReason": "UNKNOWN_ORDER_CANCEL_REASON",
      "cumFillSize": "string",
      "cumFillValue": "string",
      "cumFillFee": "string",
      "maxFillPrice": "string",
      "minFillPrice": "string",
      "cumLiquidateFee": "string",
      "cumRealizePnl": "string",
      "cumMatchSize": "string",
      "cumMatchValue": "string",
      "cumMatchFee": "string",
      "cumFailSize": "string",
      "cumFailValue": "string",
      "cumFailFee": "string",
      "cumApprovedSize": "string",
      "cumApprovedValue": "string",
      "cumApprovedFee": "string",
      "createdTime": "string",
      "updatedTime": "string"
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

<a id="opIdgetHistoryOrderPage"></a>

## GET 根据账户id翻页获取委托单

GET /api/v1/private/order/getHistoryOrderPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的委托单，如果为空则获取所有抵押品coinId的委托单|
|filterContractIdList|query|string| 否 |过滤获取指定合约的委托单；如果为空的话获取所有合约委托单|
|filterTypeList|query|string| 否 |过滤获取指定类型的委托单，不填的话所有类型委托单|
|filterStatusList|query|string| 否 |过滤获取指定状态的委托单，不填的话所有状态委托单|
|filterIsLiquidateList|query|string| 否 |过滤获取指定是否为清算的委托单，不填的话所有委托单|
|filterIsDeleverageList|query|string| 否 |过滤获取指定是否为减仓的委托单，不填的话所有委托单|
|filterIsPositionTpslList|query|string| 否 |过滤获取指定是否为仓位止盈止损单，不填的话所有委托单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的委托单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 | 过滤获取指定结束时间创建的委托单 (不包含)，不填或者为0的话就到最近|

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

<a id="opIdgetHistoryOrderFillTransactionPage"></a>

## GET 根据账户id和委托单ids批量获取成交单

GET /api/v1/private/order/getHistoryOrderFillTransactionPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的成交明细，如果为空则获取所有抵押品coinId的成交明细|
|filterContractIdList|query|string| 否 |过滤获取指定合约的委托成交明细；如果为空的话获取所有合约委托成交明细|
|filterOrderIdList|query|string| 否 |过滤获取指定委托单的成交明细；如果为空的话获取所有委托单的委托成交明细|
|filterIsLiquidateList|query|string| 否 |过滤获取指定是否为清算的委托单，不填的话所有委托单|
|filterIsDeleverageList|query|string| 否 |过滤获取指定是否为减仓的委托单，不填的话所有委托单|
|filterIsPositionTpslList|query|string| 否 |过滤获取指定是否为仓位止盈止损单，不填的话所有委托单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的委托单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 | 过滤获取指定结束时间创建的委托单 (不包含)，不填或者为0的话就到最近|

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

<a id="opIdgetHistoryOrderFillTransactionById"></a>

## GET 根据账户id和委托成交明细id批量获取委托成交明细

GET /api/v1/private/order/getHistoryOrderFillTransactionById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|orderFillTransactionIdList|query|string| 否 |委托成交明细id|

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

<a id="opIdgetHistoryOrderById"></a>

## GET 根据账户id和委托单id批量获取委托单

GET /api/v1/private/order/getHistoryOrderById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|orderIdList|query|string| 否 |委托单id|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "side": "UNKNOWN_ORDER_SIDE",
      "price": "string",
      "size": "string",
      "clientOrderId": "string",
      "type": "UNKNOWN_ORDER_TYPE",
      "timeInForce": "UNKNOWN_TIME_IN_FORCE",
      "reduceOnly": true,
      "triggerPrice": "string",
      "triggerPriceType": "UNKNOWN_PRICE_TYPE",
      "expireTime": "string",
      "sourceKey": "string",
      "isPositionTpsl": true,
      "isLiquidate": true,
      "isDeleverage": true,
      "openTpslParentOrderId": "string",
      "isSetOpenTp": true,
      "openTp": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isSetOpenSl": true,
      "openSl": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isWithoutMatch": true,
      "withoutMatchFillSize": "string",
      "withoutMatchFillValue": "string",
      "withoutMatchPeerAccountId": "string",
      "withoutMatchPeerOrderId": "string",
      "maxLeverage": "string",
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "liquidateFeeRate": "string",
      "marketLimitPrice": "string",
      "marketLimitValue": "string",
      "l2Nonce": "string",
      "l2Value": "string",
      "l2Size": "string",
      "l2LimitFee": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ORDER_STATUS",
      "matchSequenceId": "string",
      "triggerTime": "string",
      "triggerPriceTime": "string",
      "triggerPriceValue": "string",
      "cancelReason": "UNKNOWN_ORDER_CANCEL_REASON",
      "cumFillSize": "string",
      "cumFillValue": "string",
      "cumFillFee": "string",
      "maxFillPrice": "string",
      "minFillPrice": "string",
      "cumLiquidateFee": "string",
      "cumRealizePnl": "string",
      "cumMatchSize": "string",
      "cumMatchValue": "string",
      "cumMatchFee": "string",
      "cumFailSize": "string",
      "cumFailValue": "string",
      "cumFailFee": "string",
      "cumApprovedSize": "string",
      "cumApprovedValue": "string",
      "cumApprovedFee": "string",
      "createdTime": "string",
      "updatedTime": "string"
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

<a id="opIdgetHistoryOrderByClientOrderId"></a>

## GET 根据账户id和委托单id批量获取委托单

GET /api/v1/private/order/getHistoryOrderByClientOrderId

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|clientOrderIdList|query|string| 否 |委托单 client order id|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "side": "UNKNOWN_ORDER_SIDE",
      "price": "string",
      "size": "string",
      "clientOrderId": "string",
      "type": "UNKNOWN_ORDER_TYPE",
      "timeInForce": "UNKNOWN_TIME_IN_FORCE",
      "reduceOnly": true,
      "triggerPrice": "string",
      "triggerPriceType": "UNKNOWN_PRICE_TYPE",
      "expireTime": "string",
      "sourceKey": "string",
      "isPositionTpsl": true,
      "isLiquidate": true,
      "isDeleverage": true,
      "openTpslParentOrderId": "string",
      "isSetOpenTp": true,
      "openTp": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isSetOpenSl": true,
      "openSl": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isWithoutMatch": true,
      "withoutMatchFillSize": "string",
      "withoutMatchFillValue": "string",
      "withoutMatchPeerAccountId": "string",
      "withoutMatchPeerOrderId": "string",
      "maxLeverage": "string",
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "liquidateFeeRate": "string",
      "marketLimitPrice": "string",
      "marketLimitValue": "string",
      "l2Nonce": "string",
      "l2Value": "string",
      "l2Size": "string",
      "l2LimitFee": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ORDER_STATUS",
      "matchSequenceId": "string",
      "triggerTime": "string",
      "triggerPriceTime": "string",
      "triggerPriceValue": "string",
      "cancelReason": "UNKNOWN_ORDER_CANCEL_REASON",
      "cumFillSize": "string",
      "cumFillValue": "string",
      "cumFillFee": "string",
      "maxFillPrice": "string",
      "minFillPrice": "string",
      "cumLiquidateFee": "string",
      "cumRealizePnl": "string",
      "cumMatchSize": "string",
      "cumMatchValue": "string",
      "cumMatchFee": "string",
      "cumFailSize": "string",
      "cumFailValue": "string",
      "cumFailFee": "string",
      "cumApprovedSize": "string",
      "cumApprovedValue": "string",
      "cumApprovedFee": "string",
      "createdTime": "string",
      "updatedTime": "string"
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

<a id="opIdgetActiveOrderPage"></a>

## GET 分页获取账户下活动的委托单

GET /api/v1/private/order/getActiveOrderPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于200|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的活动委托单，如果为空则获取所有抵押品coinId的活动委托单|
|filterContractIdList|query|string| 否 |过滤获取对应合约的活动委托单，如果为空则获取所有合约的活动委托单|
|filterTypeList|query|string| 否 |过滤获取指定类型的委托单，不填的话所有类型委托单|
|filterStatusList|query|string| 否 |过滤获取指定状态的委托单，不填的话所有状态委托单|
|filterIsLiquidateList|query|string| 否 |过滤获取指定是否为清算的委托单，不填的话所有委托单|
|filterIsDeleverageList|query|string| 否 |过滤获取指定是否为减仓的委托单，不填的话所有委托单|
|filterIsPositionTpslList|query|string| 否 |过滤获取指定是否为仓位止盈止损单，不填的话所有委托单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的委托单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 |过滤获取指定结束时间创建的委托单 (不包含)，不填或者为0的话就到最近|

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

<h2 id="tocS_Result<List<OrderFillTransaction>>">Result<List<OrderFillTransaction>></h2>

<a id="schemaresult<list<orderfilltransaction>>"></a>
<a id="schema_Result<List<OrderFillTransaction>>"></a>
<a id="tocSresult<list<orderfilltransaction>>"></a>
<a id="tocsresult<list<orderfilltransaction>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "orderId": "string",
      "orderSide": "UNKNOWN_ORDER_SIDE",
      "fillSize": "string",
      "fillValue": "string",
      "fillFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "direction": "UNKNOWN_LIQUIDITY_DIRECTION",
      "isPositionTpsl": true,
      "isLiquidate": true,
      "isDeleverage": true,
      "isWithoutMatch": true,
      "matchSequenceId": "string",
      "matchIndex": 0,
      "matchTime": "string",
      "matchAccountId": "string",
      "matchOrderId": "string",
      "matchFillId": "string",
      "positionTransactionId": "string",
      "collateralTransactionId": "string",
      "extraType": "string",
      "extraDataJson": "string",
      "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2RejectTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l2ApprovedTime": "string",
      "createdTime": "string",
      "updatedTime": "string"
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
|data|[[OrderFillTransaction](#schemaorderfilltransaction)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_OrderFillTransaction">OrderFillTransaction</h2>

<a id="schemaorderfilltransaction"></a>
<a id="schema_OrderFillTransaction"></a>
<a id="tocSorderfilltransaction"></a>
<a id="tocsorderfilltransaction"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "orderId": "string",
  "orderSide": "UNKNOWN_ORDER_SIDE",
  "fillSize": "string",
  "fillValue": "string",
  "fillFee": "string",
  "fillPrice": "string",
  "liquidateFee": "string",
  "realizePnl": "string",
  "direction": "UNKNOWN_LIQUIDITY_DIRECTION",
  "isPositionTpsl": true,
  "isLiquidate": true,
  "isDeleverage": true,
  "isWithoutMatch": true,
  "matchSequenceId": "string",
  "matchIndex": 0,
  "matchTime": "string",
  "matchAccountId": "string",
  "matchOrderId": "string",
  "matchFillId": "string",
  "positionTransactionId": "string",
  "collateralTransactionId": "string",
  "extraType": "string",
  "extraDataJson": "string",
  "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
  "censorTxId": "string",
  "censorTime": "string",
  "censorFailCode": "string",
  "censorFailReason": "string",
  "l2TxId": "string",
  "l2RejectTime": "string",
  "l2RejectCode": "string",
  "l2RejectReason": "string",
  "l2ApprovedTime": "string",
  "createdTime": "string",
  "updatedTime": "string"
}

```

委托单成交明细

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||唯一标识|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|contractId|string(int64)|false|none||所属合约id|
|orderId|string(int64)|false|none||所属委托单id|
|orderSide|string|false|none||买卖方向|
|fillSize|string|false|none||实际成交数量|
|fillValue|string|false|none||实际成交价值|
|fillFee|string|false|none||实际成交费用|
|fillPrice|string|false|none||成交价格 (非精确值，仅展示使用)|
|liquidateFee|string|false|none||如果是清算(强平)成交，此字段为清算费用|
|realizePnl|string|false|none||实际已实现盈亏(成交包含平仓才会有值)|
|direction|string|false|none||实际成交方向|
|isPositionTpsl|boolean|false|none||是否为仓位止盈止损单|
|isLiquidate|boolean|false|none||是否是清算(强平)单成交|
|isDeleverage|boolean|false|none||是否是自动减仓单成交|
|isWithoutMatch|boolean|false|none||是否为不经过撮合直接成交的委托单|
|matchSequenceId|string(int64)|false|none||提交撮合处理后的顺序id|
|matchIndex|integer(int32)|false|none||提交撮合处理后多次成交的index|
|matchTime|string(int64)|false|none||提交撮合处理后的时间|
|matchAccountId|string(int64)|false|none||成交对手账户id|
|matchOrderId|string(int64)|false|none||成交对手委托单id|
|matchFillId|string|false|none||撮合引擎返回的成交id|
|positionTransactionId|string(int64)|false|none||关联的仓位明细id。|
|collateralTransactionId|string(int64)|false|none||关联的抵押品明细id。|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|censorStatus|string|false|none||当前审查状态|
|censorTxId|string(int64)|false|none||审查处理序号。当 censor_status=CENSOR_SUCCESS/CENSOR_FAILURE/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED 时存在|
|censorTime|string(int64)|false|none||审查处理时间。当 censor_status=CENSOR_SUCCESS/CENSOR_FAILURE/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED 时存在|
|censorFailCode|string|false|none||审查失败错误码。当 censor_status=CENSOR_FAILURE 时存在|
|censorFailReason|string|false|none||审查失败原因。当 censor_status=CENSOR_FAILURE 时存在|
|l2TxId|string(int64)|false|none||l2推送交易id。当 censor_status=CENSOR_SUCCESS/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED 时存在|
|l2RejectTime|string(int64)|false|none||l2拒绝时间。当 censor_status=L2_REJECT/L2_REJECT_APPROVED 时存在|
|l2RejectCode|string|false|none||l2拒绝错误码。当 censor_status=L2_REJECT/L2_REJECT_APPROVED 时存在|
|l2RejectReason|string|false|none||l2拒绝原因。当 censor_status=L2_REJECT/L2_REJECT_APPROVED 时存在|
|l2ApprovedTime|string(int64)|false|none||l2批次验证时间。当 status=L2_APPROVED/L2_REJECT_APPROVED 时存在|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|orderSide|UNKNOWN_ORDER_SIDE|
|orderSide|BUY|
|orderSide|SELL|
|orderSide|UNRECOGNIZED|
|direction|UNKNOWN_LIQUIDITY_DIRECTION|
|direction|MAKER|
|direction|TAKER|
|direction|UNRECOGNIZED|
|censorStatus|UNKNOWN_TRANSACTION_STATUS|
|censorStatus|INIT|
|censorStatus|CENSOR_SUCCESS|
|censorStatus|CENSOR_FAILURE|
|censorStatus|L2_APPROVED|
|censorStatus|L2_REJECT|
|censorStatus|L2_REJECT_APPROVED|
|censorStatus|UNRECOGNIZED|

<h2 id="tocS_Result<PageData<OrderFillTransaction>>">Result<PageData<OrderFillTransaction>></h2>

<a id="schemaresult<pagedata<orderfilltransaction>>"></a>
<a id="schema_Result<PageData<OrderFillTransaction>>"></a>
<a id="tocSresult<pagedata<orderfilltransaction>>"></a>
<a id="tocsresult<pagedata<orderfilltransaction>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "orderId": "string",
        "orderSide": "UNKNOWN_ORDER_SIDE",
        "fillSize": "string",
        "fillValue": "string",
        "fillFee": "string",
        "fillPrice": "string",
        "liquidateFee": "string",
        "realizePnl": "string",
        "direction": "UNKNOWN_LIQUIDITY_DIRECTION",
        "isPositionTpsl": true,
        "isLiquidate": true,
        "isDeleverage": true,
        "isWithoutMatch": true,
        "matchSequenceId": "string",
        "matchIndex": 0,
        "matchTime": "string",
        "matchAccountId": "string",
        "matchOrderId": "string",
        "matchFillId": "string",
        "positionTransactionId": "string",
        "collateralTransactionId": "string",
        "extraType": "string",
        "extraDataJson": "string",
        "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
        "censorTxId": "string",
        "censorTime": "string",
        "censorFailCode": "string",
        "censorFailReason": "string",
        "l2TxId": "string",
        "l2RejectTime": "string",
        "l2RejectCode": "string",
        "l2RejectReason": "string",
        "l2ApprovedTime": "string",
        "createdTime": "string",
        "updatedTime": "string"
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
|data|[PageDataOrderFillTransaction](#schemapagedataorderfilltransaction)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataOrderFillTransaction">PageDataOrderFillTransaction</h2>

<a id="schemapagedataorderfilltransaction"></a>
<a id="schema_PageDataOrderFillTransaction"></a>
<a id="tocSpagedataorderfilltransaction"></a>
<a id="tocspagedataorderfilltransaction"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "orderId": "string",
      "orderSide": "UNKNOWN_ORDER_SIDE",
      "fillSize": "string",
      "fillValue": "string",
      "fillFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "direction": "UNKNOWN_LIQUIDITY_DIRECTION",
      "isPositionTpsl": true,
      "isLiquidate": true,
      "isDeleverage": true,
      "isWithoutMatch": true,
      "matchSequenceId": "string",
      "matchIndex": 0,
      "matchTime": "string",
      "matchAccountId": "string",
      "matchOrderId": "string",
      "matchFillId": "string",
      "positionTransactionId": "string",
      "collateralTransactionId": "string",
      "extraType": "string",
      "extraDataJson": "string",
      "censorStatus": "UNKNOWN_TRANSACTION_STATUS",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2RejectTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l2ApprovedTime": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "nextPageOffsetData": "string"
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[OrderFillTransaction](#schemaorderfilltransaction)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Result<PageData<Order>>">Result<PageData<Order>></h2>

<a id="schemaresult<pagedata<order>>"></a>
<a id="schema_Result<PageData<Order>>"></a>
<a id="tocSresult<pagedata<order>>"></a>
<a id="tocsresult<pagedata<order>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "type": "UNKNOWN_ORDER_TYPE",
        "timeInForce": "UNKNOWN_TIME_IN_FORCE",
        "reduceOnly": true,
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "sourceKey": "string",
        "isPositionTpsl": true,
        "isLiquidate": true,
        "isDeleverage": true,
        "openTpslParentOrderId": "string",
        "isSetOpenTp": true,
        "openTp": {
          "side": "[",
          "price": "string",
          "size": "string",
          "clientOrderId": "string",
          "triggerPrice": "string",
          "triggerPriceType": "[",
          "expireTime": "string",
          "l2Nonce": "string",
          "l2Value": "string",
          "l2Size": "string",
          "l2LimitFee": "string",
          "l2ExpireTime": "string",
          "l2Signature": {}
        },
        "isSetOpenSl": true,
        "openSl": {
          "side": "[",
          "price": "string",
          "size": "string",
          "clientOrderId": "string",
          "triggerPrice": "string",
          "triggerPriceType": "[",
          "expireTime": "string",
          "l2Nonce": "string",
          "l2Value": "string",
          "l2Size": "string",
          "l2LimitFee": "string",
          "l2ExpireTime": "string",
          "l2Signature": {}
        },
        "isWithoutMatch": true,
        "withoutMatchFillSize": "string",
        "withoutMatchFillValue": "string",
        "withoutMatchPeerAccountId": "string",
        "withoutMatchPeerOrderId": "string",
        "maxLeverage": "string",
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "liquidateFeeRate": "string",
        "marketLimitPrice": "string",
        "marketLimitValue": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        },
        "extraType": "string",
        "extraDataJson": "string",
        "status": "UNKNOWN_ORDER_STATUS",
        "matchSequenceId": "string",
        "triggerTime": "string",
        "triggerPriceTime": "string",
        "triggerPriceValue": "string",
        "cancelReason": "UNKNOWN_ORDER_CANCEL_REASON",
        "cumFillSize": "string",
        "cumFillValue": "string",
        "cumFillFee": "string",
        "maxFillPrice": "string",
        "minFillPrice": "string",
        "cumLiquidateFee": "string",
        "cumRealizePnl": "string",
        "cumMatchSize": "string",
        "cumMatchValue": "string",
        "cumMatchFee": "string",
        "cumFailSize": "string",
        "cumFailValue": "string",
        "cumFailFee": "string",
        "cumApprovedSize": "string",
        "cumApprovedValue": "string",
        "cumApprovedFee": "string",
        "createdTime": "string",
        "updatedTime": "string"
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
|data|[PageDataOrder](#schemapagedataorder)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataOrder">PageDataOrder</h2>

<a id="schemapagedataorder"></a>
<a id="schema_PageDataOrder"></a>
<a id="tocSpagedataorder"></a>
<a id="tocspagedataorder"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "side": "UNKNOWN_ORDER_SIDE",
      "price": "string",
      "size": "string",
      "clientOrderId": "string",
      "type": "UNKNOWN_ORDER_TYPE",
      "timeInForce": "UNKNOWN_TIME_IN_FORCE",
      "reduceOnly": true,
      "triggerPrice": "string",
      "triggerPriceType": "UNKNOWN_PRICE_TYPE",
      "expireTime": "string",
      "sourceKey": "string",
      "isPositionTpsl": true,
      "isLiquidate": true,
      "isDeleverage": true,
      "openTpslParentOrderId": "string",
      "isSetOpenTp": true,
      "openTp": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isSetOpenSl": true,
      "openSl": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isWithoutMatch": true,
      "withoutMatchFillSize": "string",
      "withoutMatchFillValue": "string",
      "withoutMatchPeerAccountId": "string",
      "withoutMatchPeerOrderId": "string",
      "maxLeverage": "string",
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "liquidateFeeRate": "string",
      "marketLimitPrice": "string",
      "marketLimitValue": "string",
      "l2Nonce": "string",
      "l2Value": "string",
      "l2Size": "string",
      "l2LimitFee": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ORDER_STATUS",
      "matchSequenceId": "string",
      "triggerTime": "string",
      "triggerPriceTime": "string",
      "triggerPriceValue": "string",
      "cancelReason": "UNKNOWN_ORDER_CANCEL_REASON",
      "cumFillSize": "string",
      "cumFillValue": "string",
      "cumFillFee": "string",
      "maxFillPrice": "string",
      "minFillPrice": "string",
      "cumLiquidateFee": "string",
      "cumRealizePnl": "string",
      "cumMatchSize": "string",
      "cumMatchValue": "string",
      "cumMatchFee": "string",
      "cumFailSize": "string",
      "cumFailValue": "string",
      "cumFailFee": "string",
      "cumApprovedSize": "string",
      "cumApprovedValue": "string",
      "cumApprovedFee": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "nextPageOffsetData": "string"
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[Order](#schemaorder)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Order">Order</h2>

<a id="schemaorder"></a>
<a id="schema_Order"></a>
<a id="tocSorder"></a>
<a id="tocsorder"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "side": "UNKNOWN_ORDER_SIDE",
  "price": "string",
  "size": "string",
  "clientOrderId": "string",
  "type": "UNKNOWN_ORDER_TYPE",
  "timeInForce": "UNKNOWN_TIME_IN_FORCE",
  "reduceOnly": true,
  "triggerPrice": "string",
  "triggerPriceType": "UNKNOWN_PRICE_TYPE",
  "expireTime": "string",
  "sourceKey": "string",
  "isPositionTpsl": true,
  "isLiquidate": true,
  "isDeleverage": true,
  "openTpslParentOrderId": "string",
  "isSetOpenTp": true,
  "openTp": {
    "side": "UNKNOWN_ORDER_SIDE",
    "price": "string",
    "size": "string",
    "clientOrderId": "string",
    "triggerPrice": "string",
    "triggerPriceType": "UNKNOWN_PRICE_TYPE",
    "expireTime": "string",
    "l2Nonce": "string",
    "l2Value": "string",
    "l2Size": "string",
    "l2LimitFee": "string",
    "l2ExpireTime": "string",
    "l2Signature": {
      "r": "string",
      "s": "string",
      "v": "string"
    }
  },
  "isSetOpenSl": true,
  "openSl": {
    "side": "UNKNOWN_ORDER_SIDE",
    "price": "string",
    "size": "string",
    "clientOrderId": "string",
    "triggerPrice": "string",
    "triggerPriceType": "UNKNOWN_PRICE_TYPE",
    "expireTime": "string",
    "l2Nonce": "string",
    "l2Value": "string",
    "l2Size": "string",
    "l2LimitFee": "string",
    "l2ExpireTime": "string",
    "l2Signature": {
      "r": "string",
      "s": "string",
      "v": "string"
    }
  },
  "isWithoutMatch": true,
  "withoutMatchFillSize": "string",
  "withoutMatchFillValue": "string",
  "withoutMatchPeerAccountId": "string",
  "withoutMatchPeerOrderId": "string",
  "maxLeverage": "string",
  "takerFeeRate": "string",
  "makerFeeRate": "string",
  "liquidateFeeRate": "string",
  "marketLimitPrice": "string",
  "marketLimitValue": "string",
  "l2Nonce": "string",
  "l2Value": "string",
  "l2Size": "string",
  "l2LimitFee": "string",
  "l2ExpireTime": "string",
  "l2Signature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "extraType": "string",
  "extraDataJson": "string",
  "status": "UNKNOWN_ORDER_STATUS",
  "matchSequenceId": "string",
  "triggerTime": "string",
  "triggerPriceTime": "string",
  "triggerPriceValue": "string",
  "cancelReason": "UNKNOWN_ORDER_CANCEL_REASON",
  "cumFillSize": "string",
  "cumFillValue": "string",
  "cumFillFee": "string",
  "maxFillPrice": "string",
  "minFillPrice": "string",
  "cumLiquidateFee": "string",
  "cumRealizePnl": "string",
  "cumMatchSize": "string",
  "cumMatchValue": "string",
  "cumMatchFee": "string",
  "cumFailSize": "string",
  "cumFailValue": "string",
  "cumFailFee": "string",
  "cumApprovedSize": "string",
  "cumApprovedValue": "string",
  "cumApprovedFee": "string",
  "createdTime": "string",
  "updatedTime": "string"
}

```

永续合约委托单信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||委托单id。取值大于0|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|contractId|string(int64)|false|none||所属合约id|
|side|string|false|none||买卖方向|
|price|string|false|none||委托价格(最差可接受的价格), 实际为decimal类型。|
|size|string|false|none||委托数量, 实际为decimal类型|
|clientOrderId|string|false|none||客户自定义id，用于幂等校验|
|type|string|false|none||委托单类型|
|timeInForce|string|false|none||委托单执行策略。type为 LIMIT/STOP_LIMIT/TAKE_PROFIT_LIMIT 时有意义。|
|reduceOnly|boolean|false|none||是否是只减仓委托|
|triggerPrice|string|false|none||触发价格。type为 STOP_LIMIT/STOP_MARKET/TAKE_PROFIT_LIMIT/TAKE_PROFIT_MARKET 时有意义。如果为0代表字段为空。实际为decimal类型|
|triggerPriceType|string|false|none||价格类型。最新市价[默认],标记价格。。type为 STOP_LIMIT/STOP_MARKET/TAKE_PROFIT_LIMIT/TAKE_PROFIT_MARKET 时有意义。|
|expireTime|string(int64)|false|none||过期时间。|
|sourceKey|string|false|none||来源key，uuid|
|isPositionTpsl|boolean|false|none||是否为仓位止盈止损单|
|isLiquidate|boolean|false|none||是否是强平单|
|isDeleverage|boolean|false|none||是否是自动减仓单|
|openTpslParentOrderId|string(int64)|false|none||开仓止盈单，止损单的开仓单orderId|
|isSetOpenTp|boolean|false|none||是否设置开仓止盈|
|openTp|[OpenTpSl](#schemaopentpsl)|false|none||开仓止盈止损参数|
|isSetOpenSl|boolean|false|none||是否设置开仓止损|
|openSl|[OpenTpSl](#schemaopentpsl)|false|none||开仓止盈止损参数|
|isWithoutMatch|boolean|false|none||是否为不经过撮合直接场外成交的委托单|
|withoutMatchFillSize|string|false|none||场外交易成交数量 (仅当 is_without_match 为 true 时有效)|
|withoutMatchFillValue|string|false|none||场外交易成交价值 (仅当 is_without_match 为 true 时有效)|
|withoutMatchPeerAccountId|string(int64)|false|none||场外交易对手accountId (仅当 is_without_match 为 true 时有效)|
|withoutMatchPeerOrderId|string(int64)|false|none||场外交易对手orderId (仅当 is_without_match 为 true 时有效)|
|maxLeverage|string|false|none||下单时开仓杠杆倍数, 实际为decimal类型|
|takerFeeRate|string|false|none||下单时taker手续费率, 实际为decimal类型|
|makerFeeRate|string|false|none||下单时maker手续费率, 实际为decimal类型|
|liquidateFeeRate|string|false|none||下单时清算手续费率, 实际为decimal类型|
|marketLimitPrice|string|false|none||市价单提交撮合的限价 (仅市价单存在,其他情况为0), 实际为decimal类型|
|marketLimitValue|string|false|none||市价单提交撮合的限定成交价值 (仅市价单存在,其他情况为0), 实际为decimal类型|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_order_id) 前32个bit|
|l2Value|string|false|none||l2签名委托价值(实际成交价必须等于或优于 l2_value / l2_size), 与 price x size 的值可能不一样。实际为decimal类型|
|l2Size|string|false|none||l2签名委托数量, 与size字段可能不一样。实际为decimal类型|
|l2LimitFee|string|false|none||l2签名最高可以接受的下单费用|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间，单位毫秒。参与签名生成/校验时要取小时数，即 l2_expire_time / 3600000。注意此字段必须要大于等于 expire_time + 8 * 24 * 60 * 60 * 1000(8天)|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|status|string|false|none||委托单状态|
|matchSequenceId|string(int64)|false|none||撮合引擎已处理序号id|
|triggerTime|string(int64)|false|none||条件单触发时间|
|triggerPriceTime|string(int64)|false|none||条件单触发价格时间|
|triggerPriceValue|string|false|none||条件单触发价格值|
|cancelReason|string|false|none||委托单取消原因|
|cumFillSize|string(decimal)|false|none||累计审查通过后的成交数量, 实际为decimal类型|
|cumFillValue|string(decimal)|false|none||累计审查通过后的成交价值, 实际为decimal类型|
|cumFillFee|string(decimal)|false|none||累计审查通过后的成交手续费, 实际为decimal类型|
|maxFillPrice|string(decimal)|false|none||当前委托单审查通过后的最高成交价格, 实际为decimal类型|
|minFillPrice|string(decimal)|false|none||当前委托单审查通过后的最低成交价格, 实际为decimal类型|
|cumLiquidateFee|string(decimal)|false|none||累计查通过后的强平清算费, 实际为decimal类型|
|cumRealizePnl|string(decimal)|false|none||累计查通过后的已实现盈亏, 实际为decimal类型|
|cumMatchSize|string(decimal)|false|none||累计撮合数量,实际为decimal类型|
|cumMatchValue|string(decimal)|false|none||累计撮合价值,实际为decimal类型|
|cumMatchFee|string(decimal)|false|none||累计撮合手续费，实际为decimal类型|
|cumFailSize|string|false|none||累计审查失败/L2拒绝的数量, 实际为decimal类型|
|cumFailValue|string|false|none||累计审查失败/L2拒绝的价值, 实际为decimal类型|
|cumFailFee|string|false|none||累计审查失败/L2拒绝的手续费, 实际为decimal类型|
|cumApprovedSize|string|false|none||累计L2确认的数量|
|cumApprovedValue|string|false|none||累计L2确认的价值|
|cumApprovedFee|string|false|none||累计L2确认的手续费|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|side|UNKNOWN_ORDER_SIDE|
|side|BUY|
|side|SELL|
|side|UNRECOGNIZED|
|type|UNKNOWN_ORDER_TYPE|
|type|LIMIT|
|type|MARKET|
|type|STOP_LIMIT|
|type|STOP_MARKET|
|type|TAKE_PROFIT_LIMIT|
|type|TAKE_PROFIT_MARKET|
|type|UNRECOGNIZED|
|timeInForce|UNKNOWN_TIME_IN_FORCE|
|timeInForce|GOOD_TIL_CANCEL|
|timeInForce|FILL_OR_KILL|
|timeInForce|IMMEDIATE_OR_CANCEL|
|timeInForce|POST_ONLY|
|timeInForce|UNRECOGNIZED|
|triggerPriceType|UNKNOWN_PRICE_TYPE|
|triggerPriceType|ORACLE_PRICE|
|triggerPriceType|INDEX_PRICE|
|triggerPriceType|LAST_PRICE|
|triggerPriceType|ASK1_PRICE|
|triggerPriceType|BID1_PRICE|
|triggerPriceType|OPEN_INTEREST|
|triggerPriceType|UNRECOGNIZED|
|status|UNKNOWN_ORDER_STATUS|
|status|PENDING|
|status|OPEN|
|status|FILLED|
|status|CANCELING|
|status|CANCELED|
|status|UNTRIGGERED|
|status|UNRECOGNIZED|
|cancelReason|UNKNOWN_ORDER_CANCEL_REASON|
|cancelReason|USER_CANCELED|
|cancelReason|EXPIRE_CANCELED|
|cancelReason|COULD_NOT_FILL|
|cancelReason|REDUCE_ONLY_CANCELED|
|cancelReason|LIQUIDATE_CANCELED|
|cancelReason|MARGIN_NOT_ENOUGH|
|cancelReason|SYSTEM_LIMIT_EVICTED|
|cancelReason|ADMIN_CANCELED|
|cancelReason|INTERNAL_FAILED|
|cancelReason|UNRECOGNIZED|

<h2 id="tocS_L2Signature">L2Signature</h2>

<a id="schemal2signature"></a>
<a id="schema_L2Signature"></a>
<a id="tocSl2signature"></a>
<a id="tocsl2signature"></a>

```json
{
  "r": "string",
  "s": "string",
  "v": "string"
}

```

L2签名信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|r|string|false|none||bigint for hex str|
|s|string|false|none||bigint for hex str|
|v|string|false|none||bigint for hex str|

<h2 id="tocS_OpenTpSl">OpenTpSl</h2>

<a id="schemaopentpsl"></a>
<a id="schema_OpenTpSl"></a>
<a id="tocSopentpsl"></a>
<a id="tocsopentpsl"></a>

```json
{
  "side": "UNKNOWN_ORDER_SIDE",
  "price": "string",
  "size": "string",
  "clientOrderId": "string",
  "triggerPrice": "string",
  "triggerPriceType": "UNKNOWN_PRICE_TYPE",
  "expireTime": "string",
  "l2Nonce": "string",
  "l2Value": "string",
  "l2Size": "string",
  "l2LimitFee": "string",
  "l2ExpireTime": "string",
  "l2Signature": {
    "r": "string",
    "s": "string",
    "v": "string"
  }
}

```

开仓止盈止损参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|side|string|false|none||买卖方向,此字段必填|
|price|string|false|none||委托价格(最差可接受的价格), 实际为decimal类型。此字段必填，市价单时填0|
|size|string|false|none||委托数量, 实际为decimal类型。此字段必填|
|clientOrderId|string|false|none||客户自定义id，用于签名&幂等校验。此字段必填|
|triggerPrice|string|false|none||触发价格。此字段必填|
|triggerPriceType|string|false|none||价格类型。最新市价[默认],标记价格。此字段必填。|
|expireTime|string(int64)|false|none||过期时间。|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_order_id) 前32个bit|
|l2Value|string|false|none||l2签名委托价值(实际成交价必须等于或优于 l2_value / l2_price), 与 price x size 的值可能不一样。实际为decimal类型|
|l2Size|string|false|none||l2签名委托数量, 与size字段可能不一样。实际为decimal类型|
|l2LimitFee|string|false|none||l2签名最高可以接受的下单费用|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间. unix时间的小时数，至少要比 expire_time 晚10个小时|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|

#### 枚举值

|属性|值|
|---|---|
|side|UNKNOWN_ORDER_SIDE|
|side|BUY|
|side|SELL|
|side|UNRECOGNIZED|
|triggerPriceType|UNKNOWN_PRICE_TYPE|
|triggerPriceType|ORACLE_PRICE|
|triggerPriceType|INDEX_PRICE|
|triggerPriceType|LAST_PRICE|
|triggerPriceType|ASK1_PRICE|
|triggerPriceType|BID1_PRICE|
|triggerPriceType|OPEN_INTEREST|
|triggerPriceType|UNRECOGNIZED|

<h2 id="tocS_Result<List<Order>>">Result<List<Order>></h2>

<a id="schemaresult<list<order>>"></a>
<a id="schema_Result<List<Order>>"></a>
<a id="tocSresult<list<order>>"></a>
<a id="tocsresult<list<order>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "side": "UNKNOWN_ORDER_SIDE",
      "price": "string",
      "size": "string",
      "clientOrderId": "string",
      "type": "UNKNOWN_ORDER_TYPE",
      "timeInForce": "UNKNOWN_TIME_IN_FORCE",
      "reduceOnly": true,
      "triggerPrice": "string",
      "triggerPriceType": "UNKNOWN_PRICE_TYPE",
      "expireTime": "string",
      "sourceKey": "string",
      "isPositionTpsl": true,
      "isLiquidate": true,
      "isDeleverage": true,
      "openTpslParentOrderId": "string",
      "isSetOpenTp": true,
      "openTp": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isSetOpenSl": true,
      "openSl": {
        "side": "UNKNOWN_ORDER_SIDE",
        "price": "string",
        "size": "string",
        "clientOrderId": "string",
        "triggerPrice": "string",
        "triggerPriceType": "UNKNOWN_PRICE_TYPE",
        "expireTime": "string",
        "l2Nonce": "string",
        "l2Value": "string",
        "l2Size": "string",
        "l2LimitFee": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        }
      },
      "isWithoutMatch": true,
      "withoutMatchFillSize": "string",
      "withoutMatchFillValue": "string",
      "withoutMatchPeerAccountId": "string",
      "withoutMatchPeerOrderId": "string",
      "maxLeverage": "string",
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "liquidateFeeRate": "string",
      "marketLimitPrice": "string",
      "marketLimitValue": "string",
      "l2Nonce": "string",
      "l2Value": "string",
      "l2Size": "string",
      "l2LimitFee": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ORDER_STATUS",
      "matchSequenceId": "string",
      "triggerTime": "string",
      "triggerPriceTime": "string",
      "triggerPriceValue": "string",
      "cancelReason": "UNKNOWN_ORDER_CANCEL_REASON",
      "cumFillSize": "string",
      "cumFillValue": "string",
      "cumFillFee": "string",
      "maxFillPrice": "string",
      "minFillPrice": "string",
      "cumLiquidateFee": "string",
      "cumRealizePnl": "string",
      "cumMatchSize": "string",
      "cumMatchValue": "string",
      "cumMatchFee": "string",
      "cumFailSize": "string",
      "cumFailValue": "string",
      "cumFailFee": "string",
      "cumApprovedSize": "string",
      "cumApprovedValue": "string",
      "cumApprovedFee": "string",
      "createdTime": "string",
      "updatedTime": "string"
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
|data|[[Order](#schemaorder)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CancelAllOrderParam">CancelAllOrderParam</h2>

<a id="schemacancelallorderparam"></a>
<a id="schema_CancelAllOrderParam"></a>
<a id="tocScancelallorderparam"></a>
<a id="tocscancelallorderparam"></a>

```json
{
  "accountId": "string",
  "filterCoinIdList": [
    "string"
  ],
  "filterContractIdList": [
    "string"
  ],
  "filterOrderTypeList": [
    "UNKNOWN_ORDER_TYPE"
  ],
  "filterOrderStatusList": [
    "UNKNOWN_ORDER_STATUS"
  ],
  "filterIsPositionTpsl": [
    true
  ]
}

```

取消账户下所有委托单请求参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|filterCoinIdList|[string]|false|none||过滤取消对应抵押品coinId对应的活动委托单，如果为空则取消所有抵押品coinId的活动委托单|
|filterContractIdList|[string]|false|none||过滤取消对应合约的活动委托单，如果为空则取消所有合约的活动委托单|
|filterOrderTypeList|[string]|false|none||过滤取消指定类型的委托单，不填的话所有类型委托单|
|filterOrderStatusList|[string]|false|none||过滤取消指定状态的委托单，不填的话所有状态委托单|
|filterIsPositionTpsl|[boolean]|false|none||过滤只取消对应的仓位止盈止损单，如果为空的话会取消所有合约委托单|

<h2 id="tocS_Result<CancelOrderByClientOrderId>">Result<CancelOrderByClientOrderId></h2>

<a id="schemaresult<cancelorderbyclientorderid>"></a>
<a id="schema_Result<CancelOrderByClientOrderId>"></a>
<a id="tocSresult<cancelorderbyclientorderid>"></a>
<a id="tocsresult<cancelorderbyclientorderid>"></a>

```json
{
  "code": "string",
  "data": {
    "cancelResultMap": {
      "property1": "UNKNOWN_ORDER_CANCEL_RESULT",
      "property2": "UNKNOWN_ORDER_CANCEL_RESULT"
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
|data|[CancelOrderByClientOrderId](#schemacancelorderbyclientorderid)|false|none||根据ClientOrderId撤销订单响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CancelOrderByClientOrderId">CancelOrderByClientOrderId</h2>

<a id="schemacancelorderbyclientorderid"></a>
<a id="schema_CancelOrderByClientOrderId"></a>
<a id="tocScancelorderbyclientorderid"></a>
<a id="tocscancelorderbyclientorderid"></a>

```json
{
  "cancelResultMap": {
    "property1": "UNKNOWN_ORDER_CANCEL_RESULT",
    "property2": "UNKNOWN_ORDER_CANCEL_RESULT"
  }
}

```

根据ClientOrderId撤销订单响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|cancelResultMap|object|false|none||none|
|» **additionalProperties**|string|false|none||none|

#### 枚举值

|属性|值|
|---|---|
|**additionalProperties**|UNKNOWN_ORDER_CANCEL_RESULT|
|**additionalProperties**|SUCCESS|
|**additionalProperties**|SUCCESS_ORDER_CANCELING|
|**additionalProperties**|SUCCESS_ORDER_CANCELED|
|**additionalProperties**|FAILED_ORDER_NOT_FOUND|
|**additionalProperties**|FAILED_ORDER_FILLED|
|**additionalProperties**|FAILED_ORDER_UNKNOWN_STATUS|
|**additionalProperties**|UNRECOGNIZED|

<h2 id="tocS_CancelOrderByClientOrderIdParam">CancelOrderByClientOrderIdParam</h2>

<a id="schemacancelorderbyclientorderidparam"></a>
<a id="schema_CancelOrderByClientOrderIdParam"></a>
<a id="tocScancelorderbyclientorderidparam"></a>
<a id="tocscancelorderbyclientorderidparam"></a>

```json
{
  "accountId": "string",
  "clientOrderIdList": [
    "string"
  ]
}

```

根据clientId取消委托单请求参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|clientOrderIdList|[string]|true|none||委托单 client order id|

<h2 id="tocS_Result<CancelOrder>">Result<CancelOrder></h2>

<a id="schemaresult<cancelorder>"></a>
<a id="schema_Result<CancelOrder>"></a>
<a id="tocSresult<cancelorder>"></a>
<a id="tocsresult<cancelorder>"></a>

```json
{
  "code": "string",
  "data": {
    "cancelResultMap": {
      "property1": "UNKNOWN_ORDER_CANCEL_RESULT",
      "property2": "UNKNOWN_ORDER_CANCEL_RESULT"
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
|data|[CancelOrder](#schemacancelorder)|false|none||撤销订单响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CancelOrder">CancelOrder</h2>

<a id="schemacancelorder"></a>
<a id="schema_CancelOrder"></a>
<a id="tocScancelorder"></a>
<a id="tocscancelorder"></a>

```json
{
  "cancelResultMap": {
    "property1": "UNKNOWN_ORDER_CANCEL_RESULT",
    "property2": "UNKNOWN_ORDER_CANCEL_RESULT"
  }
}

```

撤销订单响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|cancelResultMap|object|false|none||none|
|» **additionalProperties**|string|false|none||none|

#### 枚举值

|属性|值|
|---|---|
|**additionalProperties**|UNKNOWN_ORDER_CANCEL_RESULT|
|**additionalProperties**|SUCCESS|
|**additionalProperties**|SUCCESS_ORDER_CANCELING|
|**additionalProperties**|SUCCESS_ORDER_CANCELED|
|**additionalProperties**|FAILED_ORDER_NOT_FOUND|
|**additionalProperties**|FAILED_ORDER_FILLED|
|**additionalProperties**|FAILED_ORDER_UNKNOWN_STATUS|
|**additionalProperties**|UNRECOGNIZED|

<h2 id="tocS_CancelOrderByIdParam">CancelOrderByIdParam</h2>

<a id="schemacancelorderbyidparam"></a>
<a id="schema_CancelOrderByIdParam"></a>
<a id="tocScancelorderbyidparam"></a>
<a id="tocscancelorderbyidparam"></a>

```json
{
  "accountId": "string",
  "orderIdList": [
    "string"
  ]
}

```

取消委托单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|orderIdList|[string]|true|none||委托单id|

<h2 id="tocS_Result<CreateOrder>">Result<CreateOrder></h2>

<a id="schemaresult<createorder>"></a>
<a id="schema_Result<CreateOrder>"></a>
<a id="tocSresult<createorder>"></a>
<a id="tocsresult<createorder>"></a>

```json
{
  "code": "string",
  "data": {
    "orderId": "string"
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
|data|[CreateOrder](#schemacreateorder)|false|none||创建订单响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CreateOrder">CreateOrder</h2>

<a id="schemacreateorder"></a>
<a id="schema_CreateOrder"></a>
<a id="tocScreateorder"></a>
<a id="tocscreateorder"></a>

```json
{
  "orderId": "string"
}

```

创建订单响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|orderId|string(int64)|false|none||委托单Id|

<h2 id="tocS_CreateOrderParam">CreateOrderParam</h2>

<a id="schemacreateorderparam"></a>
<a id="schema_CreateOrderParam"></a>
<a id="tocScreateorderparam"></a>
<a id="tocscreateorderparam"></a>

```json
{
  "accountId": "string",
  "contractId": "string",
  "side": "UNKNOWN_ORDER_SIDE",
  "size": "string",
  "price": "string",
  "clientOrderId": "string",
  "type": "UNKNOWN_ORDER_TYPE",
  "timeInForce": "UNKNOWN_TIME_IN_FORCE",
  "reduceOnly": true,
  "triggerPrice": "string",
  "triggerPriceType": "UNKNOWN_PRICE_TYPE",
  "expireTime": "string",
  "sourceKey": "string",
  "isPositionTpsl": true,
  "openTpslParentOrderId": "string",
  "isSetOpenTp": true,
  "openTp": {
    "side": "UNKNOWN_ORDER_SIDE",
    "price": "string",
    "size": "string",
    "clientOrderId": "string",
    "triggerPrice": "string",
    "triggerPriceType": "UNKNOWN_PRICE_TYPE",
    "expireTime": "string",
    "l2Nonce": "string",
    "l2Value": "string",
    "l2Size": "string",
    "l2LimitFee": "string",
    "l2ExpireTime": "string",
    "l2Signature": "string"
  },
  "isSetOpenSl": true,
  "openSl": {
    "side": "UNKNOWN_ORDER_SIDE",
    "price": "string",
    "size": "string",
    "clientOrderId": "string",
    "triggerPrice": "string",
    "triggerPriceType": "UNKNOWN_PRICE_TYPE",
    "expireTime": "string",
    "l2Nonce": "string",
    "l2Value": "string",
    "l2Size": "string",
    "l2LimitFee": "string",
    "l2ExpireTime": "string",
    "l2Signature": "string"
  },
  "l2Nonce": "string",
  "l2Value": "string",
  "l2Size": "string",
  "l2LimitFee": "string",
  "l2ExpireTime": "string",
  "l2Signature": "string",
  "extraType": "string",
  "extraDataJson": "string"
}

```

创建委托单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|contractId|string(int64)|false|none||所属合约id|
|side|string|false|none||买卖方向。此字段必填|
|size|string|false|none||委托数量, 实际为decimal类型。此字段必填|
|price|string|false|none||委托价格(最差可接受的价格), 实际为decimal类型。此字段必填，市价单填0即可。|
|clientOrderId|string|false|none||客户自定义id，用于幂等校验。此字段必填|
|type|string|false|none||委托单类型。此字段必填|
|timeInForce|string|false|none||委托单执行策略。type为 LIMIT/STOP_LIMIT/TAKE_PROFIT_LIMIT 时有意义。此字段必填，市价单必为IMMEDIATE_OR_CANCEL。|
|reduceOnly|boolean|false|none||是否是只减仓委托。此字段必填|
|triggerPrice|string|false|none||触发价格。type为 STOP_LIMIT/STOP_MARKET/TAKE_PROFIT_LIMIT/TAKE_PROFIT_MARKET 时有意义。如果为0代表字段为空。实际为decimal类型。当为条件单时必填。|
|triggerPriceType|string|false|none||价格类型。最新市价[默认],标记价格。type为条件单时有意义。当为条件单时必填。|
|expireTime|string(int64)|false|none||过期时间。|
|sourceKey|string|false|none||来源key，uuid|
|isPositionTpsl|boolean|false|none||是否为仓位止盈止损单。此字段必填，默认为false|
|openTpslParentOrderId|string(int64)|false|none||开仓止盈单，止损单的开仓单orderId|
|isSetOpenTp|boolean|false|none||是否设置开仓止盈。此字段必填|
|openTp|[OpenTpSlParam](#schemaopentpslparam)|false|none||开仓止盈止损参数|
|isSetOpenSl|boolean|false|none||是否设置开仓止损。此字段必填|
|openSl|[OpenTpSlParam](#schemaopentpslparam)|false|none||开仓止盈止损参数|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_order_id) 前32个bit|
|l2Value|string|false|none||l2签名委托价值(实际成交价必须等于或优于 l2_value / l2_price), 与 price x size 的值可能不一样。实际为decimal类型|
|l2Size|string|false|none||l2签名委托数量, 与size字段可能不一样。实际为decimal类型|
|l2LimitFee|string|false|none||l2签名最高可以接受的下单费用|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间，单位毫秒。参与签名生成/校验时要取小时数，即 l2_expire_time / 3600000。注意此字段必须要大于等于 expire_time + 8 * 24 * 60 * 60 * 1000(8天)|
|l2Signature|string|false|none||l2签名|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|

#### 枚举值

|属性|值|
|---|---|
|side|UNKNOWN_ORDER_SIDE|
|side|BUY|
|side|SELL|
|side|UNRECOGNIZED|
|type|UNKNOWN_ORDER_TYPE|
|type|LIMIT|
|type|MARKET|
|type|STOP_LIMIT|
|type|STOP_MARKET|
|type|TAKE_PROFIT_LIMIT|
|type|TAKE_PROFIT_MARKET|
|type|UNRECOGNIZED|
|timeInForce|UNKNOWN_TIME_IN_FORCE|
|timeInForce|GOOD_TIL_CANCEL|
|timeInForce|FILL_OR_KILL|
|timeInForce|IMMEDIATE_OR_CANCEL|
|timeInForce|POST_ONLY|
|timeInForce|UNRECOGNIZED|
|triggerPriceType|UNKNOWN_PRICE_TYPE|
|triggerPriceType|ORACLE_PRICE|
|triggerPriceType|INDEX_PRICE|
|triggerPriceType|LAST_PRICE|
|triggerPriceType|ASK1_PRICE|
|triggerPriceType|BID1_PRICE|
|triggerPriceType|OPEN_INTEREST|
|triggerPriceType|UNRECOGNIZED|

<h2 id="tocS_OpenTpSlParam">OpenTpSlParam</h2>

<a id="schemaopentpslparam"></a>
<a id="schema_OpenTpSlParam"></a>
<a id="tocSopentpslparam"></a>
<a id="tocsopentpslparam"></a>

```json
{
  "side": "UNKNOWN_ORDER_SIDE",
  "price": "string",
  "size": "string",
  "clientOrderId": "string",
  "triggerPrice": "string",
  "triggerPriceType": "UNKNOWN_PRICE_TYPE",
  "expireTime": "string",
  "l2Nonce": "string",
  "l2Value": "string",
  "l2Size": "string",
  "l2LimitFee": "string",
  "l2ExpireTime": "string",
  "l2Signature": "string"
}

```

开仓止盈止损参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|side|string|false|none||买卖方向,此字段必填|
|price|string|false|none||委托价格(最差可接受的价格), 实际为decimal类型。此字段必填，市价单时填0|
|size|string|false|none||委托数量, 实际为decimal类型。此字段必填|
|clientOrderId|string|false|none||客户自定义id，用于签名&幂等校验。此字段必填|
|triggerPrice|string|false|none||触发价格。此字段必填|
|triggerPriceType|string|false|none||价格类型。最新市价[默认],标记价格。此字段必填。|
|expireTime|string(int64)|false|none||过期时间。|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_order_id) 前32个bit|
|l2Value|string|false|none||l2签名委托价值(实际成交价必须等于或优于 l2_value / l2_price), 与 price x size 的值可能不一样。实际为decimal类型|
|l2Size|string|false|none||l2签名委托数量, 与size字段可能不一样。实际为decimal类型|
|l2LimitFee|string|false|none||l2签名最高可以接受的下单费用|
|l2ExpireTime|string|false|none||l2签名过期时间. unix时间的小时数，至少要比 expire_time 晚10个小时|
|l2Signature|string|false|none||l2签名|

#### 枚举值

|属性|值|
|---|---|
|side|UNKNOWN_ORDER_SIDE|
|side|BUY|
|side|SELL|
|side|UNRECOGNIZED|
|triggerPriceType|UNKNOWN_PRICE_TYPE|
|triggerPriceType|ORACLE_PRICE|
|triggerPriceType|INDEX_PRICE|
|triggerPriceType|LAST_PRICE|
|triggerPriceType|ASK1_PRICE|
|triggerPriceType|BID1_PRICE|
|triggerPriceType|OPEN_INTEREST|
|triggerPriceType|UNRECOGNIZED|

<h2 id="tocS_Result<GetMaxCreateOrderSize>">Result<GetMaxCreateOrderSize></h2>

<a id="schemaresult<getmaxcreateordersize>"></a>
<a id="schema_Result<GetMaxCreateOrderSize>"></a>
<a id="tocSresult<getmaxcreateordersize>"></a>
<a id="tocsresult<getmaxcreateordersize>"></a>

```json
{
  "code": "string",
  "data": {
    "maxBuySize": "string",
    "maxSellSize": "string",
    "ask1Price": "string",
    "bid1Price": "string"
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
|data|[GetMaxCreateOrderSize](#schemagetmaxcreateordersize)|false|none||获取最大下单数量-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetMaxCreateOrderSize">GetMaxCreateOrderSize</h2>

<a id="schemagetmaxcreateordersize"></a>
<a id="schema_GetMaxCreateOrderSize"></a>
<a id="tocSgetmaxcreateordersize"></a>
<a id="tocsgetmaxcreateordersize"></a>

```json
{
  "maxBuySize": "string",
  "maxSellSize": "string",
  "ask1Price": "string",
  "bid1Price": "string"
}

```

获取最大下单数量-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|maxBuySize|string(decimal)|false|none||最大买入size|
|maxSellSize|string(decimal)|false|none||最大卖出size|
|ask1Price|string(decimal)|false|none||最优askPrice|
|bid1Price|string(decimal)|false|none||最优bidPrice|

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

<h2 id="tocS_GetMaxCreateOrderSizeParam">GetMaxCreateOrderSizeParam</h2>

<a id="schemagetmaxcreateordersizeparam"></a>
<a id="schema_GetMaxCreateOrderSizeParam"></a>
<a id="tocSgetmaxcreateordersizeparam"></a>
<a id="tocsgetmaxcreateordersizeparam"></a>

```json
{
  "accountId": "string",
  "contractId": "string",
  "price": "string"
}

```

获取最大下单数量-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|contractId|string(int64)|false|none||所属合约id|
|price|string|false|none||下单价格|

