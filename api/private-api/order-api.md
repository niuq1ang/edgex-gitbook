# OrderPrivateApi

<a id="opIdgetMaxCreateOrderSize"></a>

## POST Get Maximum Order Creation Size

POST /api/v1/private/order/getMaxCreateOrderSize

> Body Request Parameters

```json
{
  "accountId": "string",
  "contractId": "string",
  "price": "string"
}
```

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|body|body|[GetMaxCreateOrderSizeParam](#schemagetmaxcreateordersizeparam)| No |none|

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdcreateOrder"></a>

## POST Create Order

POST /api/v1/private/order/createOrder

> Body Request Parameters

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

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CreateOrderParam](#schemacreateorderparam)| No |none|

> Response Example

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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### Response Data Structure

<a id="opIdcancelOrderById"></a>

## POST Cancel Order by Order ID

POST /api/v1/private/order/cancelOrderById

> Body Request Parameters

```json
{
  "accountId": "string",
  "orderIdList": [
    "string"
  ]
}
```

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CancelOrderByIdParam](#schemacancelorderbyidparam)| No |none|

> Response Example

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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### Response Data Structure

<a id="opIdcancelOrderByClientOrderId"></a>

## POST Cancel Order by Client Order ID

POST /api/v1/private/order/cancelOrderByClientOrderId

> Body Request Parameters

```json
{
  "accountId": "string",
  "clientOrderIdList": [
    "string"
  ]
}
```

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CancelOrderByClientOrderIdParam](#schemacancelorderbyclientorderidparam)| No |none|

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdcancelAllOrder"></a>

## POST Cancel All Orders under Account

POST /api/v1/private/order/cancelAllOrder

> Body Request Parameters

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

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CancelAllOrderParam](#schemacancelallorderparam)| No |none|

> Response Example

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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### Response Data Structure

<a id="opIdgetOrderById"></a>

## GET Get Orders by Account ID and Order IDs (Batch)

GET /api/v1/private/order/getOrderById

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|orderIdList|query|string| No |Order IDs|

> Response Example

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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### Response Data Structure

<a id="opIdgetOrderByClientOrderId"></a>

## GET Get Orders by Client Order IDs (Batch)

GET /api/v1/private/order/getOrderByClientOrderId

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|clientOrderIdList|query|string| No |Client-defined order IDs|

> Response Example

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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### Response Data Structure

<a id="opIdgetHistoryOrderPage"></a>

## GET Get Historical Orders (Paginated)

GET /api/v1/private/order/getHistoryOrderPage

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|size|query|string| No |Number of items to fetch. Must be greater than 0 and less than or equal to 100.|
|offsetData|query|string| No |Pagination offset. If not provided or empty, retrieves the first page.|
|filterCoinIdList|query|string| No |Filters by collateral coin IDs. If empty, fetches orders for all collateral coin IDs.|
|filterContractIdList|query|string| No |Filters by contract IDs. If empty, fetches orders for all contracts.|
|filterTypeList|query|string| No |Filters by order types. If empty, fetches orders of all types.|
|filterStatusList|query|string| No |Filters by order status. If empty, fetches orders of all statuses.|
|filterIsLiquidateList|query|string| No |Filters by liquidate orders. If empty, fetches all orders|
|filterIsDeleverageList|query|string| No |Filters by deleverage orders. If empty, fetches all orders|
|filterIsPositionTpslList|query|string| No |Filters by position TP/SL orders. If empty, fetches all orders|
|filterStartCreatedTimeInclusive|query|string| No |Filters orders created after or on this time (inclusive). If empty or 0, retrieves from the earliest.|
|filterEndCreatedTimeExclusive|query|string| No |Filters orders created before this time (exclusive). If empty or 0, retrieves to the latest.|

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdgetHistoryOrderFillTransactionPage"></a>

## GET Get Historical Order Fill Transactions (Paginated)

GET /api/v1/private/order/getHistoryOrderFillTransactionPage

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|size|query|string| No |Number of items to fetch. Must be greater than 0 and less than or equal to 100.|
|offsetData|query|string| No |Pagination offset. If not provided or empty, retrieves the first page.|
|filterCoinIdList|query|string| No |Filters by collateral coin IDs. If empty, fetches order fill transactions for all collateral coin IDs.|
|filterContractIdList|query|string| No |Filters by contract IDs. If empty, fetches order fill transactions for all contracts.|
|filterOrderIdList|query|string| No |Filters by order IDs. If empty, fetches order fill transactions for all orders.|
|filterIsLiquidateList|query|string| No |Filters by liquidate orders. If empty, fetches all orders|
|filterIsDeleverageList|query|string| No |Filters by deleverage orders. If empty, fetches all orders|
|filterIsPositionTpslList|query|string| No |Filters by position TP/SL orders. If empty, fetches all orders|
|filterStartCreatedTimeInclusive|query|string| No |Filters order fill transactions created after or on this time (inclusive). If empty or 0, retrieves from the earliest.|
|filterEndCreatedTimeExclusive|query|string| No |Filters order fill transactions created before this time (exclusive). If empty or 0, retrieves to the latest.|

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdgetHistoryOrderFillTransactionById"></a>

## GET Get Historical Order Fill Transactions by ID (Batch)

GET /api/v1/private/order/getHistoryOrderFillTransactionById

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|orderFillTransactionIdList|query|string| No |Order fill transaction IDs|

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdgetHistoryOrderById"></a>

## GET Get Historical Orders by ID (Batch)

GET /api/v1/private/order/getHistoryOrderById

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|orderIdList|query|string| No |Order IDs|

> Response Example

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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### Response Data Structure

<a id="opIdgetHistoryOrderByClientOrderId"></a>

## GET Get Historical Orders by Client Order IDs (Batch)

GET /api/v1/private/order/getHistoryOrderByClientOrderId

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|clientOrderIdList|query|string| No |Order client order id|

> Response Example

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
      "cumApprovedFee": "string```json
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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### Response Data Structure

<a id="opIdgetActiveOrderPage"></a>

## GET Get Active Orders (Paginated)

GET /api/v1/private/order/getActiveOrderPage

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|size|query|string| No |Number of items to fetch. Must be greater than 0 and less than or equal to 200.|
|offsetData|query|string| No |Pagination offset. If not provided or empty, retrieves the first page.|
|filterCoinIdList|query|string| No |Filters by collateral coin IDs. If empty, fetches active orders for all collateral coin IDs.|
|filterContractIdList|query|string| No |Filters by contract IDs. If empty, fetches active orders for all contracts.|
|filterTypeList|query|string| No |Filters by order types. If empty, fetches orders of all types.|
|filterStatusList|query|string| No |Filters by order status. If empty, fetches orders of all statuses.|
|filterIsLiquidateList|query|string| No |Filters by liquidate orders. If empty, fetches all orders|
|filterIsDeleverageList|query|string| No |Filters by deleverage orders. If empty, fetches all orders|
|filterIsPositionTpslList|query|string| No |Filters by position TP/SL orders. If empty, fetches all orders|
|filterStartCreatedTimeInclusive|query|string| No |Filters orders created after or on this time (inclusive). If empty or 0, retrieves from the earliest.|
|filterEndCreatedTimeExclusive|query|string| No |Filters orders created before this time (exclusive). If empty or 0, retrieves to the latest.|

> Response Example

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

# Data Models

<h2 id="tocS_Result<List<OrderFillTransaction>>">Result&lt;List&lt;OrderFillTransaction&gt;&gt;</h2>

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|data|[[OrderFillTransaction](#schemaorderfilltransaction)]|false|none|Successful response data.|
|errorParam|object|false|none|Parameter information in error messages.|
|» **additionalProperties**|string|false|none|Parameter information in error messages.|
|requestTime|string(timestamp)|false|none|Server request receive time.|
|responseTime|string(timestamp)|false|none|Server response return time.|
|traceId|string|false|none|Call trace ID.|

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

Order fill transaction details

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|id|string(int64)|false|none|Unique identifier.|
|userId|string(int64)|false|none|User ID.|
|accountId|string(int64)|false|none|Account ID.|
|coinId|string(int64)|false|none|Collateral coin ID.|
|contractId|string(int64)|false|none|Contract ID.|
|orderId|string(int64)|false|none|Order ID.|
|orderSide|string|false|none|Buy/Sell direction.|
|fillSize|string|false|none|Actual filled quantity.|
|fillValue|string|false|none|Actual filled value.|
|fillFee|string|false|none|Actual filled fee.|
|fillPrice|string|false|none|Fill price (not precise, for display purposes only).|
|liquidateFee|string|false|none|Liquidation fee if it's a liquidation (forced liquidation) transaction.|
|realizePnl|string|false|none|Realized profit and loss (only available if the fill includes closing a position).|
|direction|string|false|none|Actual fill direction.|
|isPositionTpsl|boolean|false|none|Whether this is a position take-profit/stop-loss order.|
|isLiquidate|boolean|false|none|Whether this is a liquidation (forced liquidation) fill.|
|isDeleverage|boolean|false|none|Whether this is an auto-deleverage fill.|
|isWithoutMatch|boolean|false|none|Whether this order was filled directly without matching.|
|matchSequenceId|string(int64)|false|none|Sequence ID after submitting to the matching engine.|
|matchIndex|integer(int32)|false|none|Index for multiple fills after submitting to the matching engine.|
|matchTime|string(int64)|false|none|Time after submitting to the matching engine.|
|matchAccountId|string(int64)|false|none|Counterparty account ID.|
|matchOrderId|string(int64)|false|none|Counterparty order ID.|
|matchFillId|string|false|none|Fill ID returned by the matching engine.|
|positionTransactionId|string(int64)|false|none|Associated position transaction ID.|
|collateralTransactionId|string(int64)|false|none|Associated collateral transaction ID.|
|extraType|string|false|none|Additional type for upper-layer business use.|
|extraDataJson|string|false|none|Additional data in JSON format. Defaults to an empty string.|
|censorStatus|string|false|none|Current censorship status.|
|censorTxId|string(int64)|false|none|Censorship processing sequence ID. Exists when `censor_status` is `CENSOR_SUCCESS`/`CENSOR_FAILURE`/`L2_APPROVED`/`L2_REJECT`/`L2_REJECT_APPROVED`.|
|censorTime|string(int64)|false|none|Censorship processing time. Exists when `censor_status` is `CENSOR_SUCCESS`/`CENSOR_FAILURE`/`L2_APPROVED`/`L2_REJECT`/`L2_REJECT_APPROVED`.|
|censorFailCode|string|false|none|Censorship failure error code. Exists when `censor_status` is `CENSOR_FAILURE`.|
|censorFailReason|string|false|none|Censorship failure reason. Exists when `censor_status` is `CENSOR_FAILURE`.|
|l2TxId|string(int64)|false|none|L2 push transaction ID. Exists when `censor_status` is `CENSOR_SUCCESS`/`L2_APPROVED`/`L2_REJECT`/`L2_REJECT_APPROVED`.|
|l2RejectTime|string(int64)|false|none|L2 rejection time. Exists when `censor_status` is `L2_REJECT`/`L2_REJECT_APPROVED`.|
|l2RejectCode|string|false|none|L2 rejection error code. Exists when `censor_status` is `L2_REJECT`/`L2_REJECT_APPROVED`.|
|l2RejectReason|string|false|none|L2 rejection reason. Exists when `censor_status` is `L2_REJECT`/`L2_REJECT_APPROVED`.|
|l2ApprovedTime|string(int64)|false|none|L2 batch verification time. Exists when `status` is `L2_APPROVED`/`L2_REJECT_APPROVED`.|
|createdTime|string(int64)|false|none|Creation time.|
|updatedTime|string(int64)|false|none|Update time.|

#### Enum Values

|Property|Value|
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

<h2 id="tocS_Result<PageData<OrderFillTransaction>>">Result&lt;PageData&lt;OrderFillTransaction&gt;&gt;</h2>

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|data|[PageDataOrderFillTransaction](#schemapagedataorderfilltransaction)|false|none|Generic paginated response.|
|errorParam|object|false|none|Parameter information in error messages.|
|» **additionalProperties**|string|false|none|Parameter information in error messages.|
|requestTime|string(timestamp)|false|none|Server request receive time.|
|responseTime|string(timestamp)|false|none|Server response return time.|
|traceId|string|false|none|Call trace ID.|

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

Generic paginated response.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|dataList|[[OrderFillTransaction](#schemaorderfilltransaction)]|false|none|Data list.|
|nextPageOffsetData|string|false|none|Offset for retrieving the next page. Empty string if no more data available.|

<h2 id="tocS_Result<PageData<Order>>">Result&lt;PageData&lt;Order&gt;&gt;</h2>

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|data|[PageDataOrder](#schemapagedataorder)|false|none|Generic paginated response.|
|errorParam|object|false|none|Parameter information in error messages.|
|» **additionalProperties**|string|false|none|Parameter information in error messages.|
|requestTime|string(timestamp)|false|none|Server request receive time.|
|responseTime|string(timestamp)|false|none|Server response return time.|
|traceId|string|false|none|Call trace ID.|

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

Generic paginated response.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|dataList|[[Order](#schemaorder)]|false|none|Data list.|
|nextPageOffsetData|string|false|none|Offset for retrieving the next page. Empty string if no more data available.|

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

Perpetual contract order information.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|id|string(int64)|false|none|Order ID. Value greater than 0.|
|userId|string(int64)|false|none|User ID.|
|accountId|string(int64)|false|none|Account ID.|
|coinId|string(int64)|false|none|Collateral coin ID.|
|contractId|string(int64)|false|none|Contract ID.|
|side|string|false|none|Buy/Sell direction.|
|price|string|false|none|Order price (worst acceptable price), actual type is decimal.|
|size|string|false|none|Order quantity, actual type is decimal.|
|clientOrderId|string|false|none|Client-defined ID for idempotency checks.|
|type|string|false|none|Order type.|
|timeInForce|string|false|none|Order execution policy. Relevant when `type` is `LIMIT`/`STOP_LIMIT`/`TAKE_PROFIT_LIMIT`.|
|reduceOnly|boolean|false|none|Whether this is a reduce-only order.|
|triggerPrice|string|false|none|Trigger price. Relevant when `type` is `STOP_LIMIT`/`STOP_MARKET`/`TAKE_PROFIT_LIMIT`/`TAKE_PROFIT_MARKET`. If 0, the field is empty. Actual type is decimal.|
|triggerPriceType|string|false|none|Price type: Last price, Mark price, etc. Relevant when `type` is `STOP_LIMIT`/`STOP_MARKET`/`TAKE_PROFIT_LIMIT`/`TAKE_PROFIT_MARKET`.|
|expireTime|string(int64)|false|none|Expiration time.|
|sourceKey|string|false|none|Source key, UUID.|
|isPositionTpsl|boolean|false|none|Whether this is a position take-profit/stop-loss order.|
|isLiquidate|boolean|false|none|Whether this is a liquidation (forced liquidation) order.|
|isDeleverage|boolean|false|none|Whether this is an auto-deleverage order.|
|openTpslParentOrderId|string(int64)|false|none|Order ID of the opening order for a take-profit or stop-loss order.|
|isSetOpenTp|boolean|false|none|Whether take-profit is set for opening order.|
|openTp|[OpenTpSl](#schemaopentpsl)|false|none|Take-profit/stop-loss parameters for opening order.|
|isSetOpenSl|boolean|false|none|Whether stop-loss is set for opening order.|
|openSl|[OpenTpSl](#schemaopentpsl)|false|none|Take-profit/stop-loss parameters for opening order.|
|isWithoutMatch|boolean|false|none|Whether this order is directly filled without matching.|
|withoutMatchFillSize|string|false|none|Off-exchange fill quantity (valid only when `is_without_match` is true).|
|withoutMatchFillValue|string|false|none|Off-exchange fill value (valid only when `is_without_match` is true).|
|withoutMatchPeerAccountId|string(int64)|false|none|Off-exchange counterparty account ID (valid only when `is_without_match` is true).|
|withoutMatchPeerOrderId|string(int64)|false|none|Off-exchange counterparty order ID (valid only when `is_without_match` is true).|
|maxLeverage|string|false|none|Leverage used when placing the order. Actual type is decimal.|
|takerFeeRate|string|false|none|Taker fee rate when placing the order. Actual type is decimal.|
|makerFeeRate|string|false|none|Maker fee rate when placing the order. Actual type is decimal.|
|liquidateFeeRate|string|false|none|Liquidation fee rate when placing the order. Actual type is decimal.|
|marketLimitPrice|string|false|none|Limit price for submitting market orders to the matching engine (only exists for market orders, 0 otherwise). Actual type is decimal.|
|marketLimitValue|string|false|none|Limit value for submitting market orders to the matching engine (only exists for market orders, 0 otherwise). Actual type is decimal.|
|l2Nonce|string(int64)|false|none|L2 signature nonce. Takes the first 32 bits of sha256(`client_order_id`).|
|l2Value|string|false|none|L2 signature order value (the actual filled price must be equal to or better than `l2_value` / `l2_size`). May differ from `price` x `size`. Actual type is decimal.|
|l2Size|string|false|none|L2 signature order quantity. May differ from the `size` field. Actual type is decimal.|
|l2LimitFee|string|false|none|Maximum acceptable fee for L2 signature.|
|l2ExpireTime|string(int64)|false|none|L2 signature expiration time in milliseconds. The hour value should be used when generating/verifying the signature, i.e. `l2_expire_time` / 3600000. Note that this value must be greater or equal to `expire_time` + 8 * 24 * 60 * 60 * 1000 (8 days).|
|l2Signature|[L2Signature](#schemal2signature)|false|none|L2 signature information.|
|extraType|string|false|none|Additional type for upper-layer business use.|
|extraDataJson|string|false|none|Additional data in JSON format. Defaults to an empty string.|
|status|string|false|none|Order status.|
|matchSequenceId|string(int64)|false|none|Sequence ID handled by the matching engine.|
|triggerTime|string(int64)|false|none|Conditional order trigger time.|
|triggerPriceTime|string(int64)|false|none|Conditional order trigger price time.|
|triggerPriceValue|string|false|none|Conditional order trigger price value.|
|cancelReason|string|false|none|Order cancellation reason.|
|cumFillSize|string(decimal)|false|none|Cumulative filled quantity after censorship. Actual type is decimal.|
|cumFillValue|string(decimal)|false|none|Cumulative filled value after censorship. Actual type is decimal.|
|cumFillFee|string(decimal)|false|none|Cumulative filled fee after censorship. Actual type is decimal.|
|maxFillPrice|string(decimal)|false|none|Maximum filled price for the current order after censorship. Actual type is decimal.|
|minFillPrice|string(decimal)|false|none|Minimum filled price for the current order after censorship. Actual type is decimal.|
|cumLiquidateFee|string(decimal)|false|none|Cumulative liquidation fee after censorship. Actual type is decimal.|
|cumRealizePnl|string(decimal)|false|none|Cumulative realized PnL after censorship. Actual type is decimal.|
|cumMatchSize|string(decimal)|false|none|Cumulative matched quantity. Actual type is decimal.|
|cumMatchValue|string(decimal)|false|none|Cumulative matched value. Actual type is decimal.|
|cumMatchFee|string(decimal)|false|none|Cumulative matched fee. Actual type is decimal.|
|cumFailSize|string|false|none|Cumulative failed/L2 rejected quantity. Actual type is decimal.|
|cumFailValue|string|false|none|Cumulative failed/L2 rejected value. Actual type is decimal.|
|cumFailFee|string|false|none|Cumulative failed/L2 rejected fee. Actual type is decimal.|
|cumApprovedSize|string|false|none|Cumulative quantity approved by L2.|
|cumApprovedValue|string|false|none|Cumulative value approved by L2.|
|cumApprovedFee|string|false|none|Cumulative fee approved by L2.|
|createdTime|string(int64)|false|none|Creation time.|
|updatedTime|string(int64)|false|none|Update time.|

#### Enum Values

|Property|Value|
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

L2 signature information.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|r|string|false|none|Big integer as a hex string.|
|s|string|false|none|Big integer as a hex string.|
|v|string|false|none|Big integer as a hex string.|

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

Opening order take-profit/stop-loss parameters.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|side|string|false|none|Buy/sell direction. This field is required.|
|price|string|false|none|Order price (worst acceptable price), actual type is decimal. Required, enter 0 for market orders.|
|size|string|false|none|Order quantity, actual type is decimal. Required.|
|clientOrderId|string|false|none|Client-defined ID for signature and idempotency checks. This field is required.|
|triggerPrice|string|false|none|Trigger price. This field is required.|
|triggerPriceType|string|false|none|Price type: Last price, Mark price, etc. This field is required.|
|expireTime|string(int64)|false|none|Expiration time.|
|l2Nonce|string(int64)|false|none|L2 signature nonce. Takes the first 32 bits of sha256(`client_order_id`).|
|l2Value|string|false|none|L2 signature order value (the actual filled price must be equal to or better than `l2_value` / `l2_price`). May differ from `price` x `size`. Actual type is decimal.|
|l2Size|string|false|none|L2 signature order quantity. May differ from the `size` field. Actual type is decimal.|
|l2LimitFee|string|false|none|Maximum acceptable fee for L2 signature.|
|l2ExpireTime|string(int64)|false|none|L2 signature expiration time in unix hour. Must be at least 10 hours after `expire_time`.|
|l2Signature|[L2Signature](#schemal2signature)|false|none|L2 signature information.|

#### Enum Values

|Property|Value|
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

<h2 id="tocS_Result<List<Order>>">Result&lt;List&lt;Order&gt;&gt;</h2>

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|data|[[Order](#schemaorder)]|false|none|Successful response data.|
|errorParam|object|false|none|Parameter information in error messages.|
|» **additionalProperties**|string|false|none|Parameter information in error messages.|
|requestTime|string(timestamp)|false|none|Server request receive time.|
|responseTime|string(timestamp)|false|none|Server response return time.|
|traceId|string|false|none|Call trace ID.|

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

Request parameters for canceling all orders under an account.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|accountId|string(int64)|false|none|Account ID.|
|filterCoinIdList|[string]|false|none|Filter to cancel active orders for specific collateral coin IDs. If empty, cancels all.|
|filterContractIdList|[string]|false|none|Filter to cancel active orders for specific contract IDs. If empty, cancels all.|
|filterOrderTypeList|[string]|false|none|Filter to cancel orders of specific types. If empty, cancels all types.|
|filterOrderStatusList|[string]|false|none|Filter to cancel orders of specific statuses. If empty, cancels all statuses.|
|filterIsPositionTpsl|[boolean]|false|none|Filter to cancel only corresponding position take-profit/stop-loss orders. If empty, cancels all contract orders.|

<h2 id="tocS_Result<CancelOrderByClientOrderId>">Result&lt;CancelOrderByClientOrderId&gt;</h2>

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|data|[CancelOrderByClientOrderId](#schemacancelorderbyclientorderid)|false|none|Response for canceling orders by client order IDs.|
|errorParam|object|false|none|Parameter information in error messages.|
|» **additionalProperties**|string|false|none|Parameter information in error messages.|
|requestTime|string(timestamp)|false|none|Server request receive time.|
|responseTime|string(timestamp)|false|none|Server response return time.|
|traceId|string|false|none|Call trace ID.|

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

Response for canceling orders by client order IDs.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|cancelResultMap|object|false|none|None|
|» **additionalProperties**|string|false|none|None|

#### Enum Values

|Property|Value|
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

Request parameters for canceling orders by client ID.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|accountId|string(int64)|false|none|Account ID.|
|clientOrderIdList|[string]|true|none|Order client order ID.|

<h2 id="tocS_Result<CancelOrder>">Result&lt;CancelOrder&gt;</h2>

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|data|[CancelOrder](#schemacancelorder)|false|none|Response for canceling orders.|
|errorParam|object|false|none|Parameter information in error messages.|
|» **additionalProperties**|string|false|none|Parameter information in error messages.|
|requestTime|string(timestamp)|false|none|Server request receive time.|
|responseTime|string(timestamp)|false|none|Server response return time.|
|traceId|string|false|none|Call trace ID.|

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

Response for canceling orders.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|cancelResultMap|object|false|none|None|
|» **additionalProperties**|string|false|none|None|

#### Enum Values

|Property|Value|
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

Request parameters for canceling an order.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|accountId|string(int64)|false|none|Account ID.|
|orderIdList|[string]|true|none|Order ID.|

<h2 id="tocS_Result<CreateOrder>>">Result&lt;CreateOrder&gt;</h2>

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|data|[CreateOrder](#schemacreateorder)|false|none|Response for creating orders.|
|errorParam|object|false|none|Parameter information in error messages.|
|» **additionalProperties**|string|false|none|Parameter information in error messages.|
|requestTime|string(timestamp)|false|none|Server request receive time.|
|responseTime|string(timestamp)|false|none|Server response return time.|
|traceId|string|false|none|Call trace ID.|

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

Response for creating orders.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|orderId|string(int64)|false|none|Order ID.|

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

Request parameters for creating an order.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|accountId|string(int64)|false|none|Account ID.|
|contractId|string(int64)|false|none|Contract ID.|
|side|string|false|none|Buy/sell direction. This field is required.|
|size|string|false|none|Order quantity. Actual type is decimal. This field is required.|
|price|string|false|none|Order price (worst acceptable price). Actual type is decimal. This field is required, enter 0 for market orders.|
|clientOrderId|string|false|none|Client-defined ID for idempotency checks. This field is required.|
|type|string|false|none|Order type. This field is required.|
|timeInForce|string|false|none|Order execution policy. Relevant when `type` is `LIMIT`/`STOP_LIMIT`/`TAKE_PROFIT_LIMIT`. This field is required, and should be `IMMEDIATE_OR_CANCEL` for market orders.|
|reduceOnly|boolean|false|none|Whether this is a reduce-only order. This field is required.|
|triggerPrice|string|false|none|Trigger price. Relevant when `type` is `STOP_LIMIT`/`STOP_MARKET`/`TAKE_PROFIT_LIMIT`/`TAKE_PROFIT_MARKET`. If 0, the field is empty. Actual type is decimal. Required for conditional orders.|
|triggerPriceType|string|false|none|Price type: Last price, Mark price, etc. Relevant when the order is conditional. Required for conditional orders.|
|expireTime|string(int64)|false|none|Expiration time.|
|sourceKey|string|false|none|Source key, UUID.|
|isPositionTpsl|boolean|false|none|Whether this is a position take-profit/stop-loss order. This field is required, defaults to false.|
|openTpslParentOrderId|string(int64)|false|none|Order ID of the opening order for a take-profit or stop-loss order.|
|isSetOpenTp|boolean|false|none|Whether to set take-profit for the opening order. This field is required.|
|openTp|[OpenTpSlParam](#schemaopentpslparam)|false|none|Take-profit/stop-loss parameters for the opening order.||isSetOpenSl|boolean|false|none|Whether to set stop-loss for the opening order. This field is required.|
|openSl|[OpenTpSlParam](#schemaopentpslparam)|false|none|Take-profit/stop-loss parameters for the opening order.|
|l2Nonce|string(int64)|false|none|L2 signature nonce. Takes the first 32 bits of sha256(`client_order_id`).|
|l2Value|string|false|none|L2 signature order value (the actual filled price must be equal to or better than `l2_value` / `l2_price`). May differ from `price` x `size`. Actual type is decimal.|
|l2Size|string|false|none|L2 signature order quantity. May differ from the `size` field. Actual type is decimal.|
|l2LimitFee|string|false|none|Maximum acceptable fee for L2 signature.|
|l2ExpireTime|string(int64)|false|none|L2 signature expiration time in milliseconds. The hour value should be used when generating/verifying the signature, i.e. `l2_expire_time` / 3600000. Note that this value must be greater or equal to `expire_time` + 8 * 24 * 60 * 60 * 1000 (8 days).|
|l2Signature|string|false|none|L2 signature.|
|extraType|string|false|none|Additional type for upper-layer business use.|
|extraDataJson|string|false|none|Additional data in JSON format. Defaults to an empty string.|

#### Enum Values

|Property|Value|
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

Take-profit/stop-loss parameters for opening order.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|side|string|false|none|Buy/sell direction. This field is required.|
|price|string|false|none|Order price (worst acceptable price). Actual type is decimal. This field is required, enter 0 for market orders.|
|size|string|false|none|Order quantity. Actual type is decimal. This field is required.|
|clientOrderId|string|false|none|Client-defined ID for signature and idempotency checks. This field is required.|
|triggerPrice|string|false|none|Trigger price. This field is required.|
|triggerPriceType|string|false|none|Price type: Last price, Mark price, etc. This field is required.|
|expireTime|string(int64)|false|none|Expiration time.|
|l2Nonce|string(int64)|false|none|L2 signature nonce. Takes the first 32 bits of sha256(`client_order_id`).|
|l2Value|string|false|none|L2 signature order value (the actual filled price must be equal to or better than `l2_value` / `l2_price`). May differ from `price` x `size`. Actual type is decimal.|
|l2Size|string|false|none|L2 signature order quantity. May differ from the `size` field. Actual type is decimal.|
|l2LimitFee|string|false|none|Maximum acceptable fee for L2 signature.|
|l2ExpireTime|string|false|none|L2 signature expiration time in unix hour. Must be at least 10 hours after `expire_time`.|
|l2Signature|string|false|none|L2 signature.|

#### Enum Values

|Property|Value|
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

<h2 id="tocS_Result<GetMaxCreateOrderSize>>">Result&lt;GetMaxCreateOrderSize&gt;</h2>

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|data|[GetMaxCreateOrderSize](#schemagetmaxcreateordersize)|false|none|Response for getting the maximum order size.|
|errorParam|object|false|none|Parameter information in error messages.|
|» **additionalProperties**|string|false|none|Parameter information in error messages.|
|requestTime|string(timestamp)|false|none|Server request receive time.|
|responseTime|string(timestamp)|false|none|Server response return time.|
|traceId|string|false|none|Call trace ID.|

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

Response for getting the maximum order size.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|maxBuySize|string(decimal)|false|none|Maximum buy size.|
|maxSellSize|string(decimal)|false|none|Maximum sell size.|
|ask1Price|string(decimal)|false|none|Best ask price.|
|bid1Price|string(decimal)|false|none|Best bid price.|

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

Generic response structure.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise failure.|
|msg|string|false|none|Detailed error message when an error occurs.|
|requestTime|string(int64)|false|none|Server request receive time.|
|responseTime|string(int64)|false|none|Server response return time.|

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

Request parameters for getting the maximum order size.

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|accountId|string(int64)|false|none|Account ID.|
|contractId|string(int64)|false|none|Contract ID.|
|price|string|false|none|Order price.|
