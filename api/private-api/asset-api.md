# AssetsPrivateApi

<a id="opIdcreateNormalWithdraw"></a>

## POST Create Normal Withdrawal Order

POST /api/v1/private/assets/createNormalWithdraw

> Body Request Parameters

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "clientWithdrawId": "string",
  "expireTime": "string",
  "l2Signature": "string"
}
```

### Request Parameters

| Name              | Location | Type                                 | Required | Description |
|-------------------|----------|--------------------------------------|----------|-------------|
| body              | body     | [CreateNormalWithdrawParam](#schemacreatenormalwithdrawparam) | No       | None        |

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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | [Result](#schemaresult) |

<a id="opIdcreateFastWithdraw"></a>

## POST Create Fast Withdrawal Order

POST /api/v1/private/assets/createFastWithdraw

> Body Request Parameters

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "erc20Address": "string",
  "lpAccountId": "string",
  "clientFastWithdrawId": "string",
  "expireTime": "string",
  "l2Signature": "string",
  "fee": "string",
  "factRegistryAddress": "string",
  "fact": "string",
  "chainId": "string"
}
```

### Request Parameters

| Name              | Location | Type                                 | Required | Description |
|-------------------|----------|--------------------------------------|----------|-------------|
| body              | body     | [CreateFastWithdrawRequest](#schemacreatefastwithdrawrequest) | No       | None        |

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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | [Result](#schemaresult) |

<a id="opIdcreateCrossWithdraw"></a>

## POST Create Cross-Chain Withdrawal Order

POST /api/v1/private/assets/createCrossWithdraw

> Body Request Parameters

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "erc20Address": "string",
  "lpAccountId": "string",
  "clientCrossWithdrawId": "string",
  "expireTime": "string",
  "l2Signature": "string",
  "fee": "string",
  "chainId": "string",
  "mpcAddress": "string",
  "mpcSignature": "string",
  "mpcSignTime": "string"
}
```

### Request Parameters

| Name              | Location | Type                                 | Required | Description |
|-------------------|----------|--------------------------------------|----------|-------------|
| body              | body     | [CreateCrossWithdrawParam](#schemacreatecrosswithdrawparam) | No       | None        |

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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | [Result](#schemaresult) |

<a id="opIdgetNormalWithdrawableAmount"></a>

## GET Get User's Normal Withdrawable Amount

GET /api/v1/private/assets/getNormalWithdrawableAmount

### Request Parameters

| Name    | Location | Type   | Required | Description |
|---------|----------|--------|----------|-------------|
| address | query    | string | Yes      | User address |

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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | [Result](#schemaresult) |

<a id="opIdgetNormalWithdrawById"></a>

## GET Get Normal Withdrawal Orders by Account ID and Withdrawal ID

GET /api/v1/private/assets/getNormalWithdrawById

### Request Parameters

| Name               | Location | Type   | Required | Description |
|--------------------|----------|--------|----------|-------------|
| accountId          | query    | string | No       | Account ID  |
| normalWithdrawIdList | query    | string | No       | Withdrawal ID |

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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | [Result](#schemaresult) |

<a id="opIdgetFastWithdrawSignInfo"></a>

## GET Get Information Required for Fast Withdrawal Signature

GET /api/v1/private/assets/getFastWithdrawSignInfo

### Request Parameters

| Name    | Location | Type   | Required | Description |
|---------|----------|--------|----------|-------------|
| chainId | query    | string | No       | Which chain |
| amount  | query    | string | No       | Withdrawal amount |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": {
    "lpAccountId": "string",
    "fastWithdrawL2Key": "string",
    "fastWithdrawFactRegisterAddress": "string",
    "fastWithdrawMaxAmount": "string",
    "fee": "string"
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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | Inline |

### Response Data Structure

<a id="opIdgetFastWithdrawById"></a>

## GET Get Fast Withdrawal Orders by Account ID and Withdrawal ID

GET /api/v1/private/assets/getFastWithdrawById

### Request Parameters

| Name               | Location | Type   | Required | Description |
|--------------------|----------|--------|----------|-------------|
| accountId          | query    | string | No       | Account ID  |
| fastWithdrawIdList | query    | string | No       | Withdrawal ID |

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
      "lpAccountId": "string",
      "lpAccountL2Key": "string",
      "clientFastWithdrawId": "string",
      "fee": "string",
      "chainId": "string",
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "factRegistryAddress": "string",
      "fact": "string",
      "status": "FAST_WITHDRAW_UNKNOWN",
      "collateralTransactionId": "string",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2HandleTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l1ConfirmedTx": {
        "hash": "string",
        "index": 0,
        "time": "string",
        "blockHeight": "string"
      },
      "l1ConfirmedTime": "string",
      "l1CompletedTime": "string",
      "l1RejectedReasonCode": "string",
      "l1RejectedReasonMsg": "string",
      "riskSignature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "transferOutId": "string",
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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | Inline |

### Response Data Structure

<a id="opIdgetCrossWithdrawSignInfo"></a>

## GET Get Information Required for Cross-Chain Withdrawal Signature

GET /api/v1/private/assets/getCrossWithdrawSignInfo

### Request Parameters

| Name    | Location | Type   | Required | Description |
|---------|----------|--------|----------|-------------|
| chainId | query    | string | No       | Chain ID    |
| amount  | query    | string | No       | Withdrawal amount  |

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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | [Result](#schemaresult) |

<a id="opIdgetCrossWithdrawById"></a>

## GET Get Cross-Chain Withdrawal Orders by Account ID and Withdrawal ID

GET /api/v1/private/assets/getCrossWithdrawById

### Request Parameters

| Name                 | Location | Type   | Required | Description |
|----------------------|----------|--------|----------|-------------|
| accountId            | query    | string | No       | Account ID  |
| crossWithdrawIdList  | query    | string | No       | Withdrawal ID |

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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | [Result](#schemaresult) |

<a id="opIdgetCoinRate"></a>

## GET Aggregate Query of All Deposit and Withdrawal Order Records

GET /api/v1/private/assets/getCoinRate

### Request Parameters

| Name    | Location | Type   | Required | Description |
|---------|----------|--------|----------|-------------|
| chainId | query    | string | No       | Chain ID    |
| coin    | query    | string | No       | Coin        |

> Response Example

> 200 Response

```json
{
  "code": "string",
  "data": {
    "rate": "string"
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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | Inline |

### Response Data Structure

<a id="opIdgetAllOrdersPage"></a>

## GET Aggregate Query of All Deposit and Withdrawal Order Records

GET /api/v1/private/assets/getAllOrdersPage

### Request Parameters

| Name           | Location | Type   | Required | Description                                         |
|----------------|----------|--------|----------|-----------------------------------------------------|
| accountId      | query    | string | No       | Account ID                                          |
| startTime      | query    | string | No       | Start time, Unix time in seconds                   |
| endTime        | query    | string | No       | End time, Unix time in seconds                     |
| chainId        | query    | string | No       | Chain ID                                          |
| typeList       | query    | string | No       | Order type list                                 |
| size           | query    | string | No       | Number of items per page. Must be > 0 and <= 100. |
| offsetData     | query    | string | No       | Offset for page retrieval. If not provided, returns first page |

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

| Status Code | Status Code Description | Description      | Data Model |
|-------------|-------------------------|------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default response | [Result](#schemaresult) |

# Data Models

<h2 id="tocS_Result<PageData<AssetOrder>>">Result<PageData<AssetOrder>></h2>

<a id="schemaresult<pagedata<assetorder>>"></a>
<a id="schema_Result<PageData<AssetOrder>>"></a>
<a id="tocSresult<pagedata<assetorder>>"></a>
<a id="tocsresult<pagedata<assetorder>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "orderId": "string",
        "time": "string",
        "type": "UNKNOWN_ORDER_TYPE",
        "status": 0,
        "amount": "string",
        "fee": "string",
        "txId": "string",
        "chain": "string",
        "address": "string",
        "coin": "string",
        "chainId": "string",
        "transferSenderAccountId": "string",
        "transferReceiverAccountId": "string"
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

| Name             | Type                             | Required | Constraints | Description                  | Notes                                                                 |
|------------------|----------------------------------|----------|-------------|------------------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code               | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [PageDataAssetOrder](#schemapagedataassetorder) | false    | none        | Generic paginated return |                                                                       |
| errorParam       | object                           | false    | none        | Error parameter information  |                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information  |                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time    |                                                                       |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time   |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID                  |                                                                       |

<h2 id="tocS_PageDataAssetOrder">PageDataAssetOrder</h2>

<a id="schemapagedataassetorder"></a>
<a id="schema_PageDataAssetOrder"></a>
<a id="tocSpagedataassetorder"></a>
<a id="tocspagedataassetorder"></a>

```json
{
  "dataList": [
    {
      "orderId": "string",
      "time": "string",
      "type": "UNKNOWN_ORDER_TYPE",
      "status": 0,
      "amount": "string",
      "fee": "string",
      "txId": "string",
      "chain": "string",
      "address": "string",
      "coin": "string",
      "chainId": "string",
      "transferSenderAccountId": "string",
      "transferReceiverAccountId": "string"
    }
  ],
  "nextPageOffsetData": "string"
}

```

Generic paginated return

### Properties

| Name             | Type                                 | Required | Constraints | Description                   | Notes                                               |
|------------------|--------------------------------------|----------|-------------|-------------------------------|-----------------------------------------------------|
| dataList         | [[AssetOrder](#schemaassetorder)]    | false    | none        | List of data |                                                     |
| nextPageOffsetData | string                                 | false    | none        | Offset for next page | Empty string when there are no further pages. |

<h2 id="tocS_AssetOrder">AssetOrder</h2>

<a id="schemaassetorder"></a>
<a id="schema_AssetOrder"></a>
<a id="tocSassetorder"></a>
<a id="tocsassetorder"></a>

```json
{
  "orderId": "string",
  "time": "string",
  "type": "UNKNOWN_ORDER_TYPE",
  "status": 0,
  "amount": "string",
  "fee": "string",
  "txId": "string",
  "chain": "string",
  "address": "string",
  "coin": "string",
  "chainId": "string",
  "transferSenderAccountId": "string",
  "transferReceiverAccountId": "string"
}

```

Asset order information

### Properties

| Name                  | Type            | Required | Constraints | Description                | Notes                                 |
|-----------------------|-----------------|----------|-------------|----------------------------|---------------------------------------|
| orderId               | string(int64)    | false    | none        | Order ID                    |                                       |
| time                  | string(int64)    | false    | none        | Order creation time         |                                       |
| type                  | string           | false    | none        | Order type                   |                                       |
| status                | integer(int32)  | false    | none        | Order status                |                                       |
| amount                | string           | false    | none        | Order amount                |                                       |
| fee                   | string           | false    | none        | Order fee                    |                                       |
| txId                  | string           | false    | none        | Chain tx_id                 |                                       |
| chain                 | string           | false    | none        | Chain                        |                                       |
| address               | string           | false    | none        | Address                      |                                       |
| coin                  | string           | false    | none        | Coin                       |                                       |
| chainId               | string           | false    | none        | Chain ID                  |                                       |
| transferSenderAccountId | string           | false    | none        | Transfer out account ID     |                                       |
| transferReceiverAccountId | string           | false    | none        | Transfer in account ID      |                                       |

#### Enum Values

| Property | Value                     |
|----------|---------------------------|
| type     | UNKNOWN_ORDER_TYPE        |
| type     | ORDER_TYPE_NORMAL_DEPOSIT |
| type     | ORDER_TYPE_CROSS_DEPOSIT  |
| type     | ORDER_TYPE_NORMAL_WITHDRAW|
| type     | ORDER_TYPE_CROSS_WITHDRAW |
| type     | ORDER_TYPE_FAST_WITHDRAW  |
| type     | ORDER_TYPE_TRANSFER_IN    |
| type     | ORDER_TYPE_TRANSFER_OUT   |
| type     | UNRECOGNIZED            |

<h2 id="tocS_Result<GetCoinRate>">Result<GetCoinRate></h2>

<a id="schemaresult<getcoinrate>"></a>
<a id="schema_Result<GetCoinRate>"></a>
<a id="tocSresult<getcoinrate>"></a>
<a id="tocsresult<getcoinrate>"></a>

```json
{
  "code": "string",
  "data": {
    "rate": "string"
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

| Name             | Type                            | Required | Constraints | Description                       | Notes                                                                 |
|------------------|---------------------------------|----------|-------------|-----------------------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code                   | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [GetCoinRate](#schemagetcoinrate) | false    | none        | Query coin exchange rate to USDC/USDT- Response    |                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information   |                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information   |                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time     |                                                                       |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time    |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID                   |                                                                       |

<h2 id="tocS_GetCoinRate">GetCoinRate</h2>

<a id="schemagetcoinrate"></a>
<a id="schema_GetCoinRate"></a>
<a id="tocSgetcoinrate"></a>
<a id="tocsgetcoinrate"></a>

```json
{
  "rate": "string"
}
```

Query coin exchange rate to USDC/USDT - Response

### Properties

| Name | Type   | Required | Constraints | Description | Notes |
|------|--------|----------|-------------|-------------|-------|
| rate | string | false    | none        | None        |       |

<h2 id="tocS_Result<List<CrossWithdraw>>">Result<List<CrossWithdraw>></h2>

<a id="schemaresult<list<crosswithdraw>>"></a>
<a id="schema_Result<List<CrossWithdraw>>"></a>
<a id="tocSresult<list<crosswithdraw>>"></a>
<a id="tocsresult<list<crosswithdraw>>"></a>

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
      "lpAccountId": "string",
      "lpAccountL2Key": "string",
      "clientCrossWithdrawId": "string",
      "fee": "string",
      "chainId": "string",
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "CROSS_WITHDRAW_UNKNOWN",
      "collateralTransactionId": "string",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2HandleTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l1ConfirmedTx": {
        "hash": "string",
        "index": 0,
        "time": "string",
        "blockHeight": "string"
      },
      "l1ConfirmedTime": "string",
       "l1CompletedTx": {
        "hash": "string",
        "index": 0,
        "time": "string",
        "blockHeight": "string"
      },
      "l1CompletedEthAddress": "string",
      "l1CompletedTime": "string",
      "l1RejectedReasonCode": "string",
      "l1RejectedReasonMsg": "string",
      "riskSignature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "transferOutId": "string",
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

| Name             | Type                                   | Required | Constraints | Description          | Notes                                                                 |
|------------------|----------------------------------------|----------|-------------|----------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code          | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [[CrossWithdraw](#schemacrosswithdraw)] | false    | none        | Correct response data |                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information|                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information|                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time   |                                                                      |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time    |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID          |                                                                       |

<h2 id="tocS_CrossWithdraw">CrossWithdraw</h2>

<a id="schemacrosswithdraw"></a>
<a id="schema_CrossWithdraw"></a>
<a id="tocScrosswithdraw"></a>
<a id="tocscrosswithdraw"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "erc20Address": "string",
  "lpAccountId": "string",
  "lpAccountL2Key": "string",
  "clientCrossWithdrawId": "string",
  "fee": "string",
  "chainId": "string",
  "l2Nonce": "string",
  "l2ExpireTime": "string",
  "l2Signature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "extraType": "string",
  "extraDataJson": "string",
  "status": "CROSS_WITHDRAW_UNKNOWN",
  "collateralTransactionId": "string",
  "censorTxId": "string",
  "censorTime": "string",
  "censorFailCode": "string",
  "censorFailReason": "string",
  "l2TxId": "string",
  "l2HandleTime": "string",
  "l2RejectCode": "string",
  "l2RejectReason": "string",
  "l1ConfirmedTx": {
    "hash": "string",
    "index": 0,
    "time": "string",
    "blockHeight": "string"
  },
  "l1ConfirmedTime": "string",
   "l1CompletedTx": {
    "hash": "string",
    "index": 0,
    "time": "string",
    "blockHeight": "string"
  },
  "l1CompletedEthAddress": "string",
  "l1CompletedTime": "string",
  "l1RejectedReasonCode": "string",
  "l1RejectedReasonMsg": "string",
  "riskSignature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "transferOutId": "string",
  "createdTime": "string",
  "updatedTime": "string"
}
```

Cross-chain withdrawal order

### Properties

| Name                      | Type            | Required | Constraints | Description                               | Notes                                                                           |
|---------------------------|-----------------|----------|-------------|-------------------------------------------|---------------------------------------------------------------------------------|
| id                        | string(int64)    | false    | none        | Withdrawal order ID                         |                                                                                 |
| userId                    | string(int64)    | false    | none        | User ID                                  |                                                                                 |
| accountId                 | string(int64)    | false    | none        | Account ID                               |                                                                                 |
| coinId                    | string(int64)    | false    | none        | Collateral coin ID                        |                                                                                 |
| amount                    | string           | false    | none        | Withdrawal amount                         |                                                                                 |
| ethAddress                | string           | false    | none        | ETH address for withdrawal, may differ from the account's ETH address.        |                                                                    |
| erc20Address              | string           | false    | none        | L1 ERC20 contract address for the withdrawn asset |                                                                                  |
| lpAccountId               | string(int64)    | false    | none        | LP account ID for L2 receiving user transfers |                                                                                 |
| lpAccountL2Key            | string(int64)    | false    | none        | L2 key for the receiving account         |                                                                                 |
| clientCrossWithdrawId     | string           | false    | none        | Client-defined ID for idempotent checks   |                                                                                 |
| fee                       | string           | false    | none        | Transaction fee                             |                                                                                |
| chainId                   | string           | false    | none        | Chain ID for withdrawal                   |                                                                                 |
| l2Nonce                   | string(int64)    | false    | none        | L2 signature nonce.  First 32 bits of sha256(client_withdraw_id)|                                      |
| l2ExpireTime              | string(int64)    | false    | none        | L2 signature expiration time. Unix time in hours, must be at least 24 hours after order creation.        |                                      |
| l2Signature               | [L2Signature](#schemal2signature) | false    | none        | L2 signature information            |                                                                                |
| extraType                 | string           | false    | none        | Additional type for upper-layer business usage     |                                                                                 |
| extraDataJson             | string           | false    | none        | Extra data, JSON format, defaults to empty string.  |                                                                                 |
| status                    | string           | false    | none        | Normal withdrawal order status            |                                                                                 |
| collateralTransactionId    | string           | false    | none        | Related collateral detail ID.  Exists when status=SUCCESS_XXX/FAILED_L2_REJECTED|                         |
| censorTxId                | string(int64)    | false    | none        | Censorship processing sequence number. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED |          |
| censorTime                | string(int64)    | false    | none        | Censorship processing time. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED |                                |
| censorFailCode             | string           | false    | none        | Censorship failure error code. Exists when status=FAILED_CENSOR_FAILURE |                             |
| censorFailReason           | string           | false    | none        | Censorship failure reason. Exists when status=FAILED_CENSOR_FAILURE |                                       |
| l2TxId                     | string(int64)    | false    | none        Okay, here's the continuation of the translated English API documentation:

| Name                      | Type            | Required | Constraints | Description                               | Notes                                                                           |
|---------------------------|-----------------|----------|-------------|-------------------------------------------|---------------------------------------------------------------------------------|
| l2TxId                     | string(int64)    | false    | none        | L2 transaction ID.  Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED |                                                                                  |
| l2HandleTime             | string(int64)    | false    | none        | L2 processing time.  Exists when status=SUCCESS_L1_CONFIRMING/SUCCESS_L1_WITHDRAWING/SUCCESS_L1_COMPLETED/FAILED_L2_REJECTED |      |
| l2RejectCode             | string           | false    | none        | L2 reject error code. Exists when status=FAILED_L2_REJECTED|                                        |
| l2RejectReason           | string           | false    | none        | L2 reject reason. Exists when status=FAILED_L2_REJECTED|                                         |
| l1ConfirmedTx              | [L1Tx](#schemal1tx) | false    | none        | L1 transaction information           |                                                                          |
| l1ConfirmedTime            | string(int64)    | false    | none        | L1 transaction confirmation time        |                                                                       |
| l1CompletedTx              | [L1Tx](#schemal1tx) | false    | none        | L1 transaction information           |                                                                          |
| l1CompletedEthAddress     | string           | false    | none        | L1 withdrawal completion ETH address     |                                                                        |
| l1CompletedTime            | string(int64)    | false    | none        | L1 withdrawal completion time           |                                                                          |
| l1RejectedReasonCode       | string           | false    | none        | L1 rejection reason code                |                                                                          |
| l1RejectedReasonMsg        | string           | false    | none        | L1 rejection reason message             |                                                                         |
| riskSignature              | [L2Signature](#schemal2signature) | false    | none        | L2 signature information            |                                                                                |
| transferOutId             | string(int64)    | false    | none        | Transfer out order ID                 |                                                                               |
| createdTime               | string(int64)    | false    | none        | Creation time                         |                                                                        |
| updatedTime               | string(int64)    | false    | none        | Update time                           |                                                                        |

#### Enum Values

| Property | Value                          |
|----------|--------------------------------|
| status   | CROSS_WITHDRAW_UNKNOWN         |
| status   | CROSS_WITHDRAW_PENDING_RISK_CHECKING|
| status   | CROSS_WITHDRAW_PENDING_CHECKING |
| status   | CROSS_WITHDRAW_SUCCESS_SUBMIT_CENSOR    |
| status   | CROSS_WITHDRAW_PENDING_CENSOR_CHECKING_ACCOUNT |
| status   | CROSS_WITHDRAW_PENDING_CENSORING    |
| status   | CROSS_WITHDRAW_PENDING_L2_APPROVING |
| status   | CROSS_WITHDRAW_PENDING_L1_SUBMIT  |
| status   | CROSS_WITHDRAW_PENDING_L1_CONFIRMING|
| status   | CROSS_WITHDRAW_SUCCESS            |
| status   | CROSS_WITHDRAW_FAILED_RISK_CHECK_FAILURE    |
| status   | CROSS_WITHDRAW_FAILED_TRANSFER_REJECTED     |
| status   | CROSS_WITHDRAW_FAILED_CENSOR_CHECKING_ACCOUNT_REJECTED  |
| status   | CROSS_WITHDRAW_FAILED_CENSORING    |
| status   | CROSS_WITHDRAW_FAILED_L2_REJECTED |
| status   | CROSS_WITHDRAW_FAILED_L1_SUBMIT_REJECTED  |
| status   | CROSS_WITHDRAW_FAILED_L1_REJECTED |
| status   | CROSS_WITHDRAW_FAILED_USER_BALANCE_NOT_ENOUGH |
| status   | UNRECOGNIZED                  |

<h2 id="tocS_L1Tx">L1Tx</h2>

<a id="schemal1tx"></a>
<a id="schema_L1Tx"></a>
<a id="tocSl1tx"></a>
<a id="tocsl1tx"></a>

```json
{
  "hash": "string",
  "index": 0,
  "time": "string",
  "blockHeight": "string"
}
```

L1 transaction information

### Properties

| Name        | Type            | Required | Constraints | Description                 | Notes                                 |
|-------------|-----------------|----------|-------------|-----------------------------|---------------------------------------|
| hash        | string          | false    | none        | Transaction hash            |                                       |
| index       | integer(int32)  | false    | none        | Index of the tx hash       |                                       |
| time        | string(int64)    | false    | none        | Tx chain timestamp, in milliseconds       |                                  |
| blockHeight | string(int64)    | false    | none        | Block height of the tx       |                                       |

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

L2 signature information

### Properties

| Name | Type   | Required | Constraints | Description           | Notes              |
|------|--------|----------|-------------|-----------------------|--------------------|
| r    | string | false    | none        | Bigint for hex string |                    |
| s    | string | false    | none        | Bigint for hex string |                    |
| v    | string | false    | none        | Bigint for hex string |                    |

<h2 id="tocS_Result<GetCrossWithdrawSignInfo>">Result<GetCrossWithdrawSignInfo></h2>

<a id="schemaresult<getcrosswithdrawsigninfo>"></a>
<a id="schema_Result<GetCrossWithdrawSignInfo>"></a>
<a id="tocSresult<getcrosswithdrawsigninfo>"></a>
<a id="tocsresult<getcrosswithdrawsigninfo>"></a>

```json
{
  "code": "string",
  "data": {
    "lpAccountId": "string",
    "crossWithdrawL2Key": "string",
    "crossWithdrawMaxAmount": "string",
    "fee": "string"
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

| Name             | Type                                        | Required | Constraints | Description                               | Notes                                                                 |
|------------------|---------------------------------------------|----------|-------------|-------------------------------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code                               | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [GetCrossWithdrawSignInfo](#schemagetcrosswithdrawsigninfo) | false    | none        | Get information required for cross-chain withdrawal signature - Response|                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information            |                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information            |                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time               |                                                                       |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time              |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID                              |                                                                       |

<h2 id="tocS_GetCrossWithdrawSignInfo">GetCrossWithdrawSignInfo</h2>

<a id="schemagetcrosswithdrawsigninfo"></a>
<a id="schema_GetCrossWithdrawSignInfo"></a>
<a id="tocSgetcrosswithdrawsigninfo"></a>
<a id="tocsgetcrosswithdrawsigninfo"></a>

```json
{
  "lpAccountId": "string",
  "crossWithdrawL2Key": "string",
  "crossWithdrawMaxAmount": "string",
  "fee": "string"
}
```

Get information required for cross-chain withdrawal signature - Response

### Properties

| Name                 | Type   | Required | Constraints | Description                                  | Notes                                  |
|----------------------|--------|----------|-------------|----------------------------------------------|----------------------------------------|
| lpAccountId          | string | false    | none        | LP account ID for L2 receiving user transfers |                                        |
| crossWithdrawL2Key  | string | false    | none        | L2 key for fast withdrawal account      |                                        |
| crossWithdrawMaxAmount| string | false    | none        | Maximum amount for fast cross-chain withdrawal|                                         |
| fee                   | string | false    | none        | Transaction fee                                  |                                        |

<h2 id="tocS_Result<List<FastWithdraw>>">Result<List<FastWithdraw>></h2>

<a id="schemaresult<list<fastwithdraw>>"></a>
<a id="schema_Result<List<FastWithdraw>>"></a>
<a id="tocSresult<list<fastwithdraw>>"></a>
<a id="tocsresult<list<fastwithdraw>>"></a>

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
      "lpAccountId": "string",
      "lpAccountL2Key": "string",
      "clientFastWithdrawId": "string",
      "fee": "string",
      "chainId": "string",
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "factRegistryAddress": "string",
      "fact": "string",
      "status": "FAST_WITHDRAW_UNKNOWN",
      "collateralTransactionId": "string",
      "censorTxId": "string",
      "censorTime": "string",
      "censorFailCode": "string",
      "censorFailReason": "string",
      "l2TxId": "string",
      "l2HandleTime": "string",
      "l2RejectCode": "string",
      "l2RejectReason": "string",
      "l1ConfirmedTx": {
        "hash": "string",
        "index": 0,
        "time": "string",
        "blockHeight": "string"
      },
      "l1ConfirmedTime": "string",
      "l1CompletedTime": "string",
      "l1RejectedReasonCode": "string",
      "l1RejectedReasonMsg": "string",
      "riskSignature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "transferOutId": "string",
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

| Name             | Type                                | Required | Constraints | Description          | Notes                                                                 |
|------------------|-------------------------------------|----------|-------------|----------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code          | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [[FastWithdraw](#schemafastwithdraw)] | false    | none        | Correct response data |                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information|                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information|                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time   |                                                                       |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time    |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID          |                                                                       |

<h2 id="tocS_FastWithdraw">FastWithdraw</h2>

<a id="schemafastwithdraw"></a>
<a id="schema_FastWithdraw"></a>
<a id="tocSfastwithdraw"></a>
<a id="tocsfastwithdraw"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "erc20Address": "string",
  "lpAccountId": "string",
  "lpAccountL2Key": "string",
  "clientFastWithdrawId": "string",
  "fee": "string",
  "chainId": "string",
  "l2Nonce": "string",
  "l2ExpireTime": "string",
  "l2Signature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "extraType": "string",
  "extraDataJson": "string",
   "factRegistryAddress": "string",
   "fact": "string",
  "status": "FAST_WITHDRAW_UNKNOWN",
  "collateralTransactionId": "string",
  "censorTxId": "string",
  "censorTime": "string",
  "censorFailCode": "string",
  "censorFailReason": "string",
  "l2TxId": "string",
  "l2HandleTime": "string",
  "l2RejectCode": "string",
  "l2RejectReason": "string",
   "l1ConfirmedTx": {
    "hash": "string",
    "index": 0,
    "time": "string",
    "blockHeight": "string"
  },
  "l1ConfirmedTime": "string",
  "l1CompletedTime": "string",
   "l1RejectedReasonCode": "string",
  "l1RejectedReasonMsg": "string",
    "riskSignature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "transferOutId": "string",
  "createdTime": "string",
  "updatedTime": "string"
}
```

Fast withdrawal order

### Properties

| Name                       | Type            | Required | Constraints | Description                                  | Notes                                                                           |
|----------------------------|-----------------|----------|-------------|----------------------------------------------|---------------------------------------------------------------------------------|
| id                         | string(int64)    | false    | none        | Withdrawal order ID                          |                                                                                 |
| userId                     | string(int64)    | false    | none        | User ID                                      |                                                                                 |
| accountId                  | string(int64)    | false    | none        | Account ID                                   |                                                                                 |
| coinId                     | string(int64)    | false    | none        | Collateral coin ID                           |                                                                                 |
| amount                     | string           | false    | none        | Withdrawal amount                            |                                                                                 |
| ethAddress                 | string           | false    | none        | ETH address for withdrawal, may differ from the account's ETH address.  |                                                                    |
| erc20Address               | string           | false    | none        | L1 ERC20 contract address for the withdrawn asset |                                                                                  |
| lpAccountId                | string(int64)    | false    | none        | LP account ID for L2 receiving user transfers |                                                                                 |
| lpAccountL2Key             | string(int64)    | false    | none        | L2 key for the receiving account            |                                                                                 |
| clientFastWithdrawId      | string           | false    | none        | Client-defined ID for idempotent checks     |                                                                                 |
| fee                        | string           | false    | none        | Transaction fee                             |                                                                                  |
| chainId                    | string           | false    | none        | Chain ID for withdrawal                      |                                                                                 |
| l2Nonce                    | string(int64)    | false    | none        | L2 signature nonce. First 32 bits of sha256(client_withdraw_id)        |                                           |
| l2ExpireTime               | string(int64)    | false    | none        | L2 signature expiration time. Unix time in hours, must be at least 24 hours after order creation.          |                                   |
| l2Signature                | [L2Signature](#schemal2signature) | false    | none        | L2 signature information                 |                                                                                |
| extraType                  | string           | false    | none        | Additional type for upper-layer business usage      |                                                                                 |
| extraDataJson              | string           | false    | none        | Extra data, JSON format, defaults to empty string.    |                                                                                 |
| factRegistryAddress         | string           | false    | none        | None      |                                                                                 |
| fact                      | string           | false    | none        | None                                         |                                                                                 |
| status                     | string           | false    | none        | Normal withdrawal order status             |                                                                                 |
| collateralTransactionId    | string           | false    | none        | Related collateral detail ID.  Exists when status=SUCCESS_XXX/FAILED_L2_REJECTED |                             |
| censorTxId                 | string(int64)    | false    | none        | Censorship processing sequence number. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED |          |
| censorTime                 | string(int64)    | false    | none        | Censorship processing time. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED     |                                   |
| censorFailCode              | string           | false    | none        | Censorship failure error code. Exists when status=FAILED_CENSOR_FAILURE |                                      |
| censorFailReason            | string           | false    | none        | Censorship failure reason. Exists when status=FAILED_CENSOR_FAILURE       |                                         |
| l2TxId                      | string(int64)    | false    | none        | L2 transaction ID. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED          |                                   |
| l2HandleTime             | string(int64)    | false    | none        | L2 processing time. Exists when status=SUCCESS_L1_CONFIRMING/SUCCESS_L1_WITHDRAWING/SUCCESS_L1_COMPLETED/FAILED_L2_REJECTED  |      |
| l2RejectCode             | string           | false    | none        | L2 reject error code. Exists when status=FAILED_L2_REJECTED   |                                      |
| l2RejectReason           | string           | false    | none        | L2 reject reason. Exists when status=FAILED_L2_REJECTED   |                                       |
| l1ConfirmedTx             | [L1Tx](#schemal1tx) | false    | none        | L1 transaction information                  |                                                                          |
| l1ConfirmedTime           | string(int64)    | false    | none        | L1 transaction confirmation time             |                                                                       |
| l1CompletedTime           | string(int64)    | false    | none        | L1 withdrawal completion time                |                                                                       |
| l1RejectedReasonCode      | string           | false    | none        | L1 rejection reason code                      |                                                                       |
| l1RejectedReasonMsg       | string           | false    | none        | L1 rejection reason message                   |                                                                       |
| riskSignature             | [L2Signature](#schemal2signature) | false    | none        | L2 signature information                 |                                                                                |
| transferOutId            | string(int64)    | false    | none        | Transfer out order ID                       |                                                                               |
| createdTime                | string(int64)    | false    | none        | Creation time                              |                                                                        |
| updatedTime                | string(int64)    | false    | none        | Update time                                |                                                                        |

#### Enum Values

| Property | Value                          |
|----------|--------------------------------|
| status   | FAST_WITHDRAW_UNKNOWN         |
| status   | FAST_WITHDRAW_PENDING_RISK_CHECKING|
| status   | FAST_WITHDRAW_PENDING_L1_TRY   |
| status   | FAST_WITHDRAW_PENDING_CHECKING |
| status   | FAST_WITHDRAW_PENDING_SUBMIT   |
| status   | FAST_WITHDRAW_PENDING_CHECKING_ACCOUNT   |
| status   | FAST_WITHDRAW_PENDING_CENSORING|
| status   | FAST_WITHDRAW_PENDING_L1_CONFIRM  |
| status   | FAST_WITHDRAW_PENDING_L1_CONFIRMING|
| status   | FAST_WITHDRAW_PENDING_CENSORING_CONFIRMING |
| status   | FAST_WITHDRAW_PENDING_L2_APPROVING|
| status   | FAST_WITHDRAW_SUCCESS            |
| status   | FAST_WITHDRAW_FAILED_RISK_CHECK_FAILURE    |
| status   | FAST_WITHDRAW_FAILED_L1_TRY_REJECTED |
| status   | FAST_WITHDRAW_FAILED_TRANSFER_REJECTED   |
| status   | FAST_WITHDRAW_FAILED_CHECKING_ACCOUNT_REJECTED |
| status   | FAST_WITHDRAW_FAILED_CENSORING    |
| status   | FAST_WITHDRAW_FAILED_L1_CONFIRM_REJECTED |
| status   | FAST_WITHDRAW_FAILED_L1_REJECTED |
| status   | FAST_WITHDRAW_FAILED_L2_REJECTED |
| status   | UNRECOGNIZED                  |

<h2 id="tocS_Result<GetFastWithdrawSignInfo>">Result<GetFastWithdrawSignInfo></h2>

<a id="schemaresult<getfastwithdrawsigninfo>"></a>
<a id="schema_Result<GetFastWithdrawSignInfo>"></a>
<a id="tocSresult<getfastwithdrawsigninfo>"></a>
<a id="tocsresult<getfastwithdrawsigninfo>"></a>

```json
{
  "code": "string",
  "data": {
    "lpAccountId": "string",
    "fastWithdrawL2Key": "string",
    "fastWithdrawFactRegisterAddress": "string",
    "fastWithdrawMaxAmount": "string",
    "fee": "string"
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

| Name             | Type                                        | Required | Constraints | Description                                 | Notes                                                                 |
|------------------|---------------------------------------------|----------|-------------|---------------------------------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code                                 | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [GetFastWithdrawSignInfo](#schemagetfastwithdrawsigninfo) | false    | none        | Get information required for fast withdrawal signature - Response |                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information              |                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information              |                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time                |                                                                       |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time               |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID                                |                                                                       |

<h2 id="tocS_GetFastWithdrawSignInfo">GetFastWithdrawSignInfo</h2>

<a id="schemagetfastwithdrawsigninfo"></a>
<a id="schema_GetFastWithdrawSignInfo"></a>
<a id="tocSgetfastwithdrawsigninfo"></a>
<a id="tocsgetfastwithdrawsigninfo"></a>

```json
{
  "lpAccountId": "string",
  "fastWithdrawL2Key": "string",
  "fastWithdrawFactRegisterAddress": "string",
  "fastWithdrawMaxAmount": "string",
  "fee": "string"
}
```

Get information required for fast withdrawal signature - Response

### Properties

| Name                         | Type   | Required | Constraints | Description                                  | Notes                                  |
|------------------------------|--------|----------|-------------|----------------------------------------------|----------------------------------------|
| lpAccountId                  | string | false    | none        | LP account ID for L2 receiving user transfers |                                        |
| fastWithdrawL2Key           | string | false    | none        | L2 key for fast withdrawal account      |                                        |
| fastWithdrawFactRegisterAddress | string | false    | none        | L1 Fact contract address    |                                        |
| fastWithdrawMaxAmount        | string | false    | none        | Maximum amount for fast withdrawal    |                                        |
| fee                           | string | false    | none        | Fast withdrawal transaction fee        |                                        |

<h2 id="tocS_Result<List<NormalWithdraw>>">Result<List<NormalWithdraw>></h2>

<a id="schemaresult<list<normalwithdraw>>"></a>
<a id="schema_Result<List<NormalWithdraw>>"></a>
<a id="tocSresult<list<normalwithdraw>>"></a>
<a id="tocsresult<list<normalwithdraw>>"></a>

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
      "clientWithdrawId": "string",
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "status": "NORMAL_WITHDRAW_UNKNOWN",
      "tradeWithdrawId": "string",
      "riskSignature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "l1ConfirmedTx": {
        "hash": "string",
        "index": 0,
        "time": "string",
        "blockHeight": "string"
      },
      "l1ConfirmedTime": "string",
      "l1CompletedTime": "string",
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

| Name             | Type                                   | Required | Constraints | Description          | Notes                                                                 |
|------------------|----------------------------------------|----------|-------------|----------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code          | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [[NormalWithdraw](#schemanormalwithdraw)] | false    | none        | Correct response data |                                                                       |
| errorParam       | object                           | false    | none        | Error parameter information|                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information|                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time   |                                                                      |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time    |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID          |                                                                       |

<h2 id="tocS_NormalWithdraw">NormalWithdraw</h2>

<a id="schemanormalwithdraw"></a>
<a id="schema_NormalWithdraw"></a>
<a id="tocSnormalwithdraw"></a>
<a id="tocsnormalwithdraw"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "clientWithdrawId": "string",
  "l2Nonce": "string",
  "l2ExpireTime": "string",
  "l2Signature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "status": "NORMAL_WITHDRAW_UNKNOWN",
  "tradeWithdrawId": "string",
   "riskSignature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "l1ConfirmedTx": {
    "hash": "string",
    "index": 0,
    "time": "string",
    "blockHeight": "string"
  },
  "l1ConfirmedTime": "string",
  "l1CompletedTime": "string",
  "createdTime": "string",
  "updatedTime": "string"
}
```

Normal withdrawal order

### Properties

| Name                | Type            | Required | Constraints | Description                                 | Notes                                                                           |
|---------------------|-----------------|----------|-------------|---------------------------------------------|---------------------------------------------------------------------------------|
| id                  | string(int64)    | false    | none        | Withdrawal order ID                         |                                                                                 |
| userId              | string(int64)    | false    | none        | User ID                                     |                                                                                 |
| accountId           | string(int64)    | false    | none        | Account ID                                   |                                                                                 |
| coinId              | string(int64)    | false    | none        | Collateral coin ID                           |                                                                                 |
| amount              | string           | false    | none        | Withdrawal amount                            |                                                                                 |
| ethAddress          | string           | false    | none        | ETH address for withdrawal, may differ from the account's ETH address.  |                                                                    |
| clientWithdrawId     | string           | false    | none        | Client-defined ID for idempotent checks     |                                                                                 |
| l2Nonce             | string(int64)    | false    | none        | L2 signature nonce. First 32 bits of sha256(client_withdraw_id)          |                                           |
| l2ExpireTime        | string(int64)    | false    | none        | L2 signature expiration time. Unix time in hours, must be at least 24 hours after order creation.   |                                           |
| l2Signature         | [L2Signature](#schemal2signature) | false    | none        | L2 signature information                |                                                                                |
| status              | string           | false    | none        | Normal withdrawal order status            |                                                                                 |
| tradeWithdrawId       | string(int64)   | false    | none        | Corresponding trading service withdraw order ID    |                                                                                 |
| riskSignature        | [L2Signature](#schemal2signature) | false    | none        | L2 signature information                |                                                                                |
| l1ConfirmedTx         | [L1Tx](#schemal1tx) | false    | none        | L1 transaction information                  |                                                                          |
| l1ConfirmedTime       | string(int64)    | false    | none        | L1 transaction confirmation time             |                                                                       |
| l1CompletedTime       | string(int64)    | false    | none        | L1 withdrawal completion time                |                                                                       |
| createdTime           | string(int64)    | false    | none        | Creation time                              |                                                                        |
| updatedTime           | string(int64)    | false    | none        | Update time                                |                                                                        |

#### Enum Values

| Property | Value                              |
|----------|------------------------------------|
| status   | NORMAL_WITHDRAW_UNKNOWN           |
| status   | NORMAL_WITHDRAW_PENDING_RISK_CHECKING |
| status   | NORMAL_WITHDRAW_PENDING_TRADE_PROCESSING |
| status   | NORMAL_WITHDRAW_PENDING_L2_APPROVING |
| status   | NORMAL_WITHDRAW_PENDING_L1_CONFIRMING|
| status   | NORMAL_WITHDRAW_PENDING_L1_WITHDRAWING|
| status   | NORMAL_WITHDRAW_SUCCESS_L1_COMPLETED |
| status   | NORMAL_WITHDRAW_FAILED_RISK_CHECK_FAILURE   |
| status   | NORMAL_WITHDRAW_FAILED_CENSOR_FAILURE      |
| status   | NORMAL_WITHDRAW_FAILED_L2_REJECTED  |
| status   | UNRECOGNIZED                    |

<h2 id="tocS_Result<GetNormalWithdrawableAmount>">Result<GetNormalWithdrawableAmount></h2>

<a id="schemaresult<getnormalwithdrawableamount>"></a>
<a id="schema_Result<GetNormalWithdrawableAmount>"></a>
<a id="tocSresult<getnormalwithdrawableamount>"></a>
<a id="tocsresult<getnormalwithdrawableamount>"></a>

```json
{
  "code": "string",
  "data": {
    "amount": "string"
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

| Name             | Type                                          Okay, continuing the translated documentation:

| Name             | Type                                          | Required | Constraints | Description                                 | Notes                                                                 |
|------------------|-----------------------------------------------|----------|-------------|---------------------------------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code                                 | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [GetNormalWithdrawableAmount](#schemagetnormalwithdrawableamount) | false    | none        | Query normal withdrawable claim amount by user address - Response |                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information              |                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information              |                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time                |                                                                       |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time               |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID                                |                                                                       |

<h2 id="tocS_GetNormalWithdrawableAmount">GetNormalWithdrawableAmount</h2>

<a id="schemagetnormalwithdrawableamount"></a>
<a id="schema_GetNormalWithdrawableAmount"></a>
<a id="tocSgetnormalwithdrawableamount"></a>
<a id="tocsgetnormalwithdrawableamount"></a>

```json
{
  "amount": "string"
}
```

Query normal withdrawable claim amount by user address - Response

### Properties

| Name   | Type   | Required | Constraints | Description         | Notes    |
|--------|--------|----------|-------------|---------------------|----------|
| amount | string | false    | none        | Withdrawable amount |          |

<h2 id="tocS_Result<CreateCrossWithdraw>">Result<CreateCrossWithdraw></h2>

<a id="schemaresult<createcrosswithdraw>"></a>
<a id="schema_Result<CreateCrossWithdraw>"></a>
<a id="tocSresult<createcrosswithdraw>"></a>
<a id="tocsresult<createcrosswithdraw>"></a>

```json
{
  "code": "string",
  "data": {
    "crossWithdrawId": "string"
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

| Name             | Type                                     | Required | Constraints | Description            | Notes                                                                 |
|------------------|------------------------------------------|----------|-------------|------------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code            | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [CreateCrossWithdraw](#schemacreatecrosswithdraw) | false    | none        | Create cross-chain withdrawal order - Response  |                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information        |                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information        |                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time           |                                                                      |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time          |                                                                      |
| traceId          | string                           | false    | none        | Call trace ID            |                                                                       |

<h2 id="tocS_CreateCrossWithdraw">CreateCrossWithdraw</h2>

<a id="schemacreatecrosswithdraw"></a>
<a id="schema_CreateCrossWithdraw"></a>
<a id="tocScreatecrosswithdraw"></a>
<a id="tocscreatecrosswithdraw"></a>

```json
{
  "crossWithdrawId": "string"
}
```

Create cross-chain withdrawal order - Response

### Properties

| Name            | Type           | Required | Constraints | Description            | Notes    |
|-----------------|----------------|----------|-------------|------------------------|----------|
| crossWithdrawId | string(int64) | false    | none        | Cross-chain withdrawal order ID |          |

<h2 id="tocS_CreateCrossWithdrawParam">CreateCrossWithdrawParam</h2>

<a id="schemacreatecrosswithdrawparam"></a>
<a id="schema_CreateCrossWithdrawParam"></a>
<a id="tocScreatecrosswithdrawparam"></a>
<a id="tocscreatecrosswithdrawparam"></a>

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "erc20Address": "string",
  "lpAccountId": "string",
  "clientCrossWithdrawId": "string",
  "expireTime": "string",
  "l2Signature": "string",
  "fee": "string",
  "chainId": "string",
   "mpcAddress": "string",
    "mpcSignature": "string",
    "mpcSignTime": "string"
}
```

Create cross-chain withdrawal order - Request

### Properties

| Name                | Type            | Required | Constraints | Description                                | Notes                               |
|---------------------|-----------------|----------|-------------|--------------------------------------------|-------------------------------------|
| accountId           | string(int64)   | false    | none        | Account ID                                 |                                     |
| coinId              | string(int64)   | false    | none        | Coin ID                                    |                                     |
| amount              | string          | false    | none        | Withdrawal amount                          |                                     |
| ethAddress          | string          | false    | none        | Withdrawal address. If empty, withdraw to the corresponding address of the current account. |                                     |
| erc20Address       | string          | false    | none        | L1 ERC20 contract address for the withdrawn asset|                                     |
| lpAccountId         | string          | false    | none        | LP account ID for L2 receiving user transfers|                                     |
| clientCrossWithdrawId| string          | false    | none        | Client-defined ID, used for signature & idempotent check. Must be filled.|      |
| expireTime          | string(int64)   | false    | none        | Expiration time                         |                                     |
| l2Signature         | string          | false    | none        | L2 signature                             |                                     |
| fee                 | string          | false    | none        | Gas + fee obtained from front-end           |                                     |
| chainId             | string          | false    | none        | Chain ID for withdrawal                    |                                     |
| mpcAddress         | string          | false    | none        | Which mpc address initiated the withdraw | |
| mpcSignature         | string          | false    | none        |  Signature of the mpc address to the withdraw field| |
| mpcSignTime         | string          | false    | none        | mpc signature timestamp,unix timestamp in seconds     |    |

<h2 id="tocS_Result<CreateFastWithdraw>">Result<CreateFastWithdraw></h2>

<a id="schemaresult<createfastwithdraw>"></a>
<a id="schema_Result<CreateFastWithdraw>"></a>
<a id="tocSresult<createfastwithdraw>"></a>
<a id="tocsresult<createfastwithdraw>"></a>

```json
{
  "code": "string",
  "data": {
    "fastWithdrawId": "string"
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

| Name             | Type                                   | Required | Constraints | Description          | Notes                                                                 |
|------------------|----------------------------------------|----------|-------------|----------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code          | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [CreateFastWithdraw](#schemacreatefastwithdraw) | false    | none        | Create fast withdrawal order - Response     |                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information|                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information|                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time   |                                                                      |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time    |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID          |                                                                       |

<h2 id="tocS_CreateFastWithdraw">CreateFastWithdraw</h2>

<a id="schemacreatefastwithdraw"></a>
<a id="schema_CreateFastWithdraw"></a>
<a id="tocScreatefastwithdraw"></a>
<a id="tocscreatefastwithdraw"></a>

```json
{
  "fastWithdrawId": "string"
}
```

Create fast withdrawal order - Response

### Properties

| Name           | Type           | Required | Constraints | Description           | Notes    |
|----------------|----------------|----------|-------------|-----------------------|----------|
| fastWithdrawId | string(int64) | false    | none        | Fast withdrawal order ID |          |

<h2 id="tocS_CreateFastWithdrawRequest">CreateFastWithdrawRequest</h2>

<a id="schemacreatefastwithdrawrequest"></a>
<a id="schema_CreateFastWithdrawRequest"></a>
<a id="tocScreatefastwithdrawrequest"></a>
<a id="tocscreatefastwithdrawrequest"></a>

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "erc20Address": "string",
  "lpAccountId": "string",
  "clientFastWithdrawId": "string",
  "expireTime": "string",
  "l2Signature": "string",
  "fee": "string",
  "factRegistryAddress": "string",
  "fact": "string",
  "chainId": "string"
}
```

Create fast withdrawal order - Request

### Properties

| Name                 | Type            | Required | Constraints | Description                                 | Notes                                   |
|----------------------|-----------------|----------|-------------|---------------------------------------------|-----------------------------------------|
| accountId            | string(int64)   | false    | none        | Account ID                                  |                                         |
| coinId               | string(int64)   | false    | none        | Coin ID                                     |                                         |
| amount               | string          | false    | none        | Withdrawal amount                           |                                         |
| ethAddress           | string          | false    | none        | Withdrawal address. If empty, withdraw to the corresponding address of the current account. | |
| erc20Address         | string          | false    | none        | L1 ERC20 contract address for the withdrawn asset   |                                         |
| lpAccountId          | string          | false    | none        | LP account ID for L2 receiving user transfers |                                         |
| clientFastWithdrawId  | string          | false    | none        | Client-defined ID, used for signature & idempotent check. Must be filled.   |                                         |
| expireTime           | string(int64)   | false    | none        | Expiration time                             |                                         |
| l2Signature          | string          | false    | none        | L2 signature                                 |                                         |
| fee                  | string          | false    | none        | Gas + fee obtained from front-end            |                                         |
| factRegistryAddress   | string          | false    | none        | Fact contract address corresponding to fast withdrawal |                                          |
| fact                | string          | false    | none        | Fact value corresponding to fast withdrawal  |                                         |
| chainId              | string          | false    | none        | Chain ID for withdrawal                     |                                         |

<h2 id="tocS_Result<CreateNormalWithdraw>">Result<CreateNormalWithdraw></h2>

<a id="schemaresult<createnormalwithdraw>"></a>
<a id="schema_Result<CreateNormalWithdraw>"></a>
<a id="tocSresult<createnormalwithdraw>"></a>
<a id="tocsresult<createnormalwithdraw>"></a>

```json
{
  "code": "string",
  "data": {
    "withdrawId": "string"
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

| Name             | Type                                    | Required | Constraints | Description              | Notes                                                                 |
|------------------|-----------------------------------------|----------|-------------|--------------------------|-----------------------------------------------------------------------|
| code             | string                           | false    | none        | Status code              | Returns "SUCCESS" for success, otherwise it's a failure.                |
| data             | [CreateNormalWithdraw](#schemacreatenormalwithdraw) | false    | none        | Create normal withdrawal order - Response  |                                                                      |
| errorParam       | object                           | false    | none        | Error parameter information          |                                                                       |
| » **additionalProperties** | string                           | false    | none        | Error parameter information          |                                                                       |
| requestTime      | string(timestamp)                 | false    | none        | Server request receive time             |                                                                      |
| responseTime     | string(timestamp)                 | false    | none        | Server response return time            |                                                                       |
| traceId          | string                           | false    | none        | Call trace ID              |                                                                       |

<h2 id="tocS_CreateNormalWithdraw">CreateNormalWithdraw</h2>

<a id="schemacreatenormalwithdraw"></a>
<a id="schema_CreateNormalWithdraw"></a>
<a id="tocScreatenormalwithdraw"></a>
<a id="tocscreatenormalwithdraw"></a>

```json
{
  "withdrawId": "string"
}
```

Create normal withdrawal order - Response

### Properties

| Name       | Type           | Required | Constraints | Description           | Notes    |
|------------|----------------|----------|-------------|-----------------------|----------|
| withdrawId | string(int64) | false    | none        | Withdrawal order ID  |          |

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

General response structure

### Properties

| Name         | Type       | Required | Constraints | Description                                   | Notes                                 |
|--------------|------------|----------|-------------|-----------------------------------------------|---------------------------------------|
| code         | string     | false    | none        | Status code. Returns "SUCCESS" for success, otherwise it's a failure. |                         |
| msg          | string     | false    | none        | Detailed error message when an error occurs     |                                       |
| requestTime  | string(int64) | false    | none        | Server request receive time                      |                                       |
| responseTime | string(int64) | false    | none        | Server response return time                     |                                       |

<h2 id="tocS_CreateNormalWithdrawParam">CreateNormalWithdrawParam</h2>

<a id="schemacreatenormalwithdrawparam"></a>
<a id="schema_CreateNormalWithdrawParam"></a>
<a id="tocScreatenormalwithdrawparam"></a>
<a id="tocscreatenormalwithdrawparam"></a>

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "clientWithdrawId": "string",
  "expireTime": "string",
  "l2Signature": "string"
}
```

Create normal withdrawal order - Request

### Properties

| Name             | Type            | Required | Constraints | Description                                | Notes                                 |
|------------------|-----------------|----------|-------------|--------------------------------------------|---------------------------------------|
| accountId        | string(int64)   | false    | none        | Account ID                                 |                                       |
| coinId           | string(int64)   | false    | none        | Coin ID                                    |                                       |
| amount           | string          | false    | none        | Withdrawal amount                          |                                       |
| ethAddress       | string          | false    | none        | Withdrawal address. If empty, withdraw to the corresponding address of the current account.  |                                      |
| clientWithdrawId  | string          | false    | none        | Client-defined ID, used for signature & idempotent check. Must be filled.   |                                       |
| expireTime       | string(int64)  | false    | none        | Expiration time                           |                                       |
| l2Signature      | string          | false    | none        | L2 signature                                |                                       |
