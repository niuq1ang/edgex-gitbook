# WithdrawPrivateApi

<a id="opIdcreateWithdraw"></a>

## POST Create Withdrawal Order

POST /api/v1/private/withdraw/createWithdraw

> Body Request Parameters

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "erc20Address": "string",
  "clientWithdrawId": "string",
  "riskSignature": "string",
  "l2Nonce": "string",
  "l2ExpireTime": "string",
  "l2Signature": "string",
  "extraType": "string",
  "extraDataJson": "string"
}
```

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CreateWithdrawParam](#schemacreatewithdrawparam)| No |none|

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresultcreatewithdraw)|

<a id="opIdgetWithdrawById"></a>

## GET Get Withdrawal Orders in Batch by ID

GET /api/v1/private/withdraw/getWithdrawById

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|withdrawIdList|query|string| No |Withdrawal order ID|

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
      "amount": "string",
      "ethAddress": "string",
      "erc20Address": "string",
      "clientWithdrawId": "string",
      "riskSignature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_WITHDRAW_STATUS",
      "collateralTransactionId": "string",
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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresultlistwithdraw)|

### Response Data Structure

<a id="opIdgetWithdrawByClientWithdrawId"></a>

## GET Get Withdrawal Orders in Batch by Client ID

GET /api/v1/private/withdraw/getWithdrawByClientWithdrawId

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|clientWithdrawIdList|query|string| No |Withdrawal order ID|

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
      "amount": "string",
      "ethAddress": "string",
      "erc20Address": "string",
      "clientWithdrawId": "string",
      "riskSignature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_WITHDRAW_STATUS",
      "collateralTransactionId": "string",
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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresultlistwithdraw)|

### Response Data Structure

<a id="opIdgetWithdrawAvailableAmount"></a>

## GET Get Available Withdrawal Amount

GET /api/v1/private/withdraw/getWithdrawAvailableAmount

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|coinId|query|string| No |Coin ID|

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresultgetwithdrawavailableamount)|

<a id="opIdgetActiveWithdraw"></a>

## GET Get Active Withdrawal Orders with Pagination

GET /api/v1/private/withdraw/getActiveWithdraw

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|accountId|query|string| No |Account ID|
|size|query|string| No |Number of items to get. Must be greater than 0 and less than or equal to 100|
|offsetData|query|string| No |Pagination offset. If empty, get the first page|
|filterCoinIdList|query|string| No |Filter by withdrawal order with the corresponding collateral coinId, if empty, get all coinIds' withdrawal orders|
|filterStatusList|query|string| No |Filter by withdrawal order with the specified status, if empty, get all status' withdrawal orders|
|filterStartCreatedTimeInclusive|query|string| No |Filter by withdrawal order created after this time (inclusive), if empty or 0, start from the earliest|
|filterEndCreatedTimeExclusive|query|string| No |Filter by withdrawal order created before this time (exclusive), if empty or 0, end with the latest|

> Response Example

> 200 Response

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
        "amount": "string",
        "ethAddress": "string",
        "erc20Address": "string",
        "clientWithdrawId": "string",
        "riskSignature": {
          "r": "string",
          "s": "string",
          "v": "string"
        },
        "l2Nonce": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        },
        "extraType": "string",
        "extraDataJson": "string",
        "status": "UNKNOWN_WITHDRAW_STATUS",
        "collateralTransactionId": "string",
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

### Response

|Status Code|Status Code Description|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresultpagedatawithdraw)|

### Response Data Structure

# Data Models

<a id="schemaresultpagedatawithdraw"></a>
### Withdrawal Response

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|code|string|false|none||Status code. "SUCCESS" if successful, otherwise it's a failure|
|data|[PageDataWithdraw](#schemapagedatawithdraw)|false|none||Generic pagination response|
|errorParam|object|false|none||Parameter information in the error message|
|requestTime|string(timestamp)|false|none||Server request receiving time|
|responseTime|string(timestamp)|false|none||Server response return time|
|traceId|string|false|none||Call traceId|


<a id="schemapagedatawithdraw"></a>
### Withdrawal Data List

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|dataList|[[Withdraw](#schemawithdraw)]|false|none||Data list|
|nextPageOffsetData|string|false|none||Offset for getting the next page. Empty string if there is no next page|

<h2 id="tocS_Withdraw">Withdraw</h2>

<a id="schemawithdraw"></a>
### Withdrawal Order

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|id|string(int64)|false|none||Withdrawal order ID|
|userId|string(int64)|false|none||User ID|
|accountId|string(int64)|false|none||Account ID|
|coinId|string(int64)|false|none||Collateral coin ID|
|amount|string|false|none||Withdrawal amount|
|ethAddress|string|false|none||Withdrawal address.|
|erc20Address|string|false|none||Withdrawal coin contract address|
|clientWithdrawId|string|false|none||Client defined ID, used for idempotent verification|
|riskSignature|[L2Signature](#schemal2signature)|false|none||L2 signature information|
|l2Nonce|string(int64)|false|none||L2 signature nonce. Take the first 32 bits of sha256(client_withdraw_id)|
|l2ExpireTime|string(int64)|false|none||L2 signature expiration time, in milliseconds. When generating/verifying the signature, the number of hours should be taken, i.e., l2_expire_time / 3600000|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2 signature information|
|extraType|string|false|none||Additional type, for use by upper-level services|
|extraDataJson|string|false|none||Additional data, JSON format, default is empty string|
|status|string|false|none||Withdrawal order status|
|collateralTransactionId|string(int64)|false|none||Associated collateral transaction ID. Exists when status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED|
|censorTxId|string(int64)|false|none||Censor processing sequence number. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED|
|censorTime|string(int64)|false|none||Censor processing time. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED|
|censorFailCode|string|false|none||Censor failure error code. Exists when status=FAILED_CENSOR_FAILURE|
|censorFailReason|string|false|none||Censor failure reason. Exists when status=FAILED_CENSOR_FAILURE|
|l2TxId|string(int64)|false|none||L2 push transaction ID. Exists when censor_status=CENSOR_SUCCESS/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED|
|l2RejectTime|string(int64)|false|none||L2 rejection time. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED|
|l2RejectCode|string|false|none||L2 rejection error code. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED|
|l2RejectReason|string|false|none||L2 rejection reason. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED|
|l2ApprovedTime|string(int64)|false|none||L2 batch verification time. Exists when status=L2_APPROVED/L2_REJECT_APPROVED|
|createdTime|string(int64)|false|none||Creation time|
|updatedTime|string(int64)|false|none||Update time|

#### Enum Values

|Property|Value|
|---|---|
|status|UNKNOWN_WITHDRAW_STATUS|
|status|PENDING_CENSORING|
|status|SUCCESS_CENSOR_SUCCESS|
|status|SUCCESS_L2_APPROVED|
|status|FAILED_CENSOR_FAILURE|
|status|FAILED_L2_REJECT|
|status|FAILED_L2_REJECT_APPROVED|
|status|UNRECOGNIZED|


<a id="schemal2signature"></a>
### L2 signature information

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|r|string|false|none||bigint for hex str|
|s|string|false|none||bigint for hex str|
|v|string|false|none||bigint for hex str|


<a id="schemaresultgetwithdrawavailableamount"></a>
### Get available withdrawal amount Response

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|code|string|false|none||Status code. "SUCCESS" if successful, otherwise it's a failure|
|data|[GetWithdrawAvailableAmount](#schemagetwithdrawavailableamount)|false|none||Get available withdrawal amount - response|
|errorParam|object|false|none||Parameter information in the error message|
|requestTime|string(timestamp)|false|none||Server request receiving time|
|responseTime|string(timestamp)|false|none||Server response return time|
|traceId|string|false|none||Call traceId|


<a id="schemagetwithdrawavailableamount"></a>
### Get available withdrawal amount Data

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|availableAmount|string(decimal)|false|none||Available amount|


<a id="schemaresultlistwithdraw"></a>
### Withdraw List Response

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|code|string|false|none||Status code. "SUCCESS" if successful, otherwise it's a failure|
|data|[[Withdraw](#schemawithdraw)]|false|none||Correct response data|
|errorParam|object|false|none||Parameter information in the error message|
|requestTime|string(timestamp)|false|none||Server request receiving time|
|responseTime|string(timestamp)|false|none||Server response return time|
|traceId|string|false|none||Call traceId|


<a id="schemaresultcreatewithdraw"></a>
### Create withdrawal order Response

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|code|string|false|none||Status code. "SUCCESS" if successful, otherwise it's a failure|
|data|[CreateWithdraw](#schemacreatewithdraw)|false|none||Create withdrawal order - response|
|errorParam|object|false|none||Parameter information in the error message|
|requestTime|string(timestamp)|false|none||Server request receiving time|
|responseTime|string(timestamp)|false|none||Server response return time|
|traceId|string|false|none||Call traceId|


<a id="schemacreatewithdraw"></a>
<### Create withdrawal order response

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|withdrawId|string(int64)|false|none||Withdrawal order ID|

<a id="schemacreatewithdrawparam"></a>
### Create withdrawal order request

|Name|Type|Required|Constraints|Alias|Description|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||Account ID|
|coinId|string(int64)|false|none||Coin ID|
|amount|string(decimal)|false|none||Withdrawal amount|
|ethAddress|string|false|none||Withdrawal address.|
|erc20Address|string|false|none||Withdrawal coin contract address|
|clientWithdrawId|string|false|none||Client defined ID, used for idempotent verification|
|riskSignature|string|false|none||Risk control signature|
|l2Nonce|string(int64)|false|none||L2 signature nonce. Take the first 32 bits of sha256(client_withdraw_id)|
|l2ExpireTime|string(int64)|false|none||L2 signature expiration time, in milliseconds. When generating/verifying the signature, the number of hours should be taken, i.e., l2_expire_time / 3600000|
|l2Signature|string|false|none||L2 signature|
|extraType|string|false|none||Additional type, for use by upper-level services|
|extraDataJson|string|false|none||Additional data, JSON format, default is empty string|
```
