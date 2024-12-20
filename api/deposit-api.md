# DepositPrivateApi

<a id="opIdrequestRelayerSignAndBroadcast"></a>

## POST Create Relayer Deposit Order

POST /api/v1/private/deposit/requestRelayerSignAndBroadcast

> Body Request Parameters

```json
{
  "deadline": "string",
  "r": "string",
  "s": "string",
  "v": "string",
  "type": "string",
  "amount": "string",
  "owner": "string",
  "starkKey": "string",
  "positionId": "string",
  "chainId": "string",
  "mpcSignature": "string"
}
```

### Request Parameters

| Name        | Location | Type                                  | Required | Description |
| ----------- | -------- | ------------------------------------- | -------- | ----------- |
| body        | body     | [RequestRelayerSignAndBroadcastParam](#schemarequestrelayersignandbroadcastparam) | No       | none        |

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

| Status Code | Status Code Meaning                                                                       | Description     | Data Model     |
| ----------- | ----------------------------------------------------------------------------------------- | --------------- | -------------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#resultrequestrelayersignandbroadcast>) |

<a id="opIdcreateDeposit"></a>

## POST Create Deposit Order

POST /api/v1/private/deposit/createDeposit

> Body Request Parameters

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "ethAddress": "string",
  "erc20Address": "string",
  "clientDepositId": "string",
  "l1Tx": {
    "hash": "string",
    "index": 0,
    "time": "string",
    "blockHeight": "string"
  },
  "riskSignature": "string",
  "l2Key": "string",
  "extraType": "string",
  "extraDataJson": "string"
}
```

### Request Parameters

| Name            | Location | Type                      | Required | Description |
| --------------- | -------- | ------------------------- | -------- | ----------- |
| body            | body     | [CreateDepositParam](#schemacreatedepositparam) | No       | none        |

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

| Status Code | Status Code Meaning                                                                       | Description     | Data Model     |
| ----------- | ----------------------------------------------------------------------------------------- | --------------- | -------------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult<createdeposit>) |

<a id="opIdgetDepositById"></a>

## GET Get Deposit Orders by ID in Batch

GET /api/v1/private/deposit/getDepositById

### Request Parameters

| Name            | Location | Type   | Required | Description      |
| --------------- | -------- | ------ | -------- | ---------------- |
| accountId       | query    | string | No       | Account ID       |
| depositIdList   | query    | string | No       | Deposit Order IDs |

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

| Status Code | Status Code Meaning                                                                       | Description     | Data Model     |
| ----------- | ----------------------------------------------------------------------------------------- | --------------- | -------------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult<list<deposit>>) |

<a id="opIdgetDepositByClientDepositId"></a>

## GET Get Deposit Orders by Account ID and Client Deposit ID in Batch

GET /api/v1/private/deposit/getDepositByClientDepositId

### Request Parameters

| Name                | Location | Type   | Required | Description             |
| ------------------- | -------- | ------ | -------- | ----------------------- |
| accountId           | query    | string | No       | Account ID              |
| clientDepositIdList | query    | string | No       | Client-defined Deposit IDs |

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

| Status Code | Status Code Meaning                                                                       | Description     | Data Model     |
| ----------- | ----------------------------------------------------------------------------------------- | --------------- | -------------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult<list<deposit>>) |

<a id="opIdgetActiveDeposit"></a>

## GET Get Paged Deposit Orders

GET /api/v1/private/deposit/getActiveDeposit

### Request Parameters

| Name         | Location | Type   | Required | Description                                                 |
| ------------ | -------- | ------ | -------- | ----------------------------------------------------------- |
| accountId    | query    | string | No       | Account ID                                                  |
| size         | query    | string | No       | Number of records to retrieve. Must be greater than 0 and less than or equal to 100 |
| offsetData   | query    | string | No       | Offset for pagination. If empty or not provided, retrieves the first page |

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
        "clientDepositId": "string",
        "l1Tx": {
          "hash": "string",
          "index": 0,
          "time": "string",
          "blockHeight": "string"
        },
        "riskSignature": {
          "r": "string",
          "s": "string",
          "v": "string"
        },
        "l2Key": "string",
        "extraType": "string",
        "extraDataJson": "string",
        "status": "UNKNOWN_DEPOSIT_STATUS",
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

| Status Code | Status Code Meaning                                                                       | Description     | Data Model     |
| ----------- | ----------------------------------------------------------------------------------------- | --------------- | -------------- |
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult<pagedata<deposit>>)] |

### Response Structure

# Data Models

<a id="schemaresult<pagedata<deposit>>"></a>
### Deposit Order Response

| Name           | Type                                  | Required | Constraints | Description     | Notes                                 |
| -------------- | ------------------------------------- | -------- | ----------- | --------------- | ------------------------------------- |
| code           | string                                | false    | none        |                 | Status code. "SUCCESS" if successful, otherwise failure |
| data           | [PageDataDeposit](#schemapagedatadeposit) | false    | none        |                 | Generic paged response                |
| errorParam     | object                                | false    | none        |                 | Parameter information in the error message |
| requestTime    | string(timestamp)                     | false    | none        |                 | Server request receive time           |
| responseTime   | string(timestamp)                     | false    | none        |                 | Server response return time           |
| traceId        | string                                | false    | none        |                 | Invocation trace ID                  |


<a id="schemapagedatadeposit"></a>
### Deposit Order Page Data

| Name               | Type                        | Required | Constraints | Description                       | Notes                                |
| ------------------ | --------------------------- | -------- | ----------- | --------------------------------- | ------------------------------------ |
| dataList           | [[Deposit](#schemadeposit)] | false    | none        | List of data                      |                                      |
| nextPageOffsetData | string                      | false    | none        | Offset for next page. Empty string if no more data | |

<a id="schemadeposit"></a>
### Deposit Order Data

| Name                     | Type                               | Required | Constraints | Description                                                              | Notes                                                                                   |
| ------------------------ | ---------------------------------- | -------- | ----------- | ------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- |
| id                       | string(int64)                      | false    | none        | Deposit order ID                                                       |                                                                                         |
| userId                   | string(int64)                      | false    | none        | User ID                                                                  |                                                                                         |
| accountId                | string(int64)                      | false    | none        | Account ID                                                               |                                                                                         |
| coinId                   | string(int64)                      | false    | none        | Collateral coin ID                                                       |                                                                                         |
| amount                   | string                             | false    | none        | Deposit amount                                                           |                                                                                         |
| ethAddress               | string                             | false    | none        | Deposit ETH address. Might be different from the address in the account  |                                                                                         |
| erc20Address             | string                             | false    | none        | Deposit coin contract address                                            |                                                                                         |
| clientDepositId          | string                             | false    | none        | Client-defined ID for idempotency                                        |                                                                                         |
| l1Tx                     | [L1Tx](#schemal1tx)                | false    | none        | L1 transaction information                                             |                                                                                         |
| riskSignature            | [L2Signature](#schemal2signature)  | false    | none        | L2 signature information                                                 |                                                                                         |
| l2Key                    | string                             | false    | none        | L2 recipient account key                                                 |                                                                                         |
| extraType                | string                             | false    | none        | Additional type for upper-layer business usage                            |                                                                                         |
| extraDataJson            | string                             | false    | none        | Extra data in JSON format, default is empty string                      |                                                                                         |
| status                   | string                             | false    | none        | Deposit order status                                                     |                                                                                         |
| collateralTransactionId  | string(int64)                      | false    | none        | Associated collateral detail ID. Present when status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED | |
| censorTxId               | string(int64)                      | false    | none        | Censor processing sequence number. Present when status=SUCCESS_XXX/FAILED_XXX |                                                                                         |
| censorTime               | string(int64)                      | false    | none        | Censor processing time. Present when status=SUCCESS_XXX/FAILED_XXX      |                                                                                         |
| censorFailCode           | string                             | false    | none        | Censor failure error code. Present when status=FAILED_CENSOR_FAILURE    |                                                                                         |
| censorFailReason         | string                             | false    | none        | Censor failure reason. Present when status=FAILED_CENSOR_FAILURE      |                                                                                         |
| l2TxId                   | string(int64)                      | false    | none        | L2 push transaction ID. Present when status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |                                                                                         |
| l2RejectTime             | string(int64)                      | false    | none        | L2 rejection time. Present when status=FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |                                                                                         |
| l2RejectCode             | string                             | false    | none        | L2 rejection error code. Present when status=FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |                                                                                         |
| l2RejectReason           | string                             | false    | none        | L2 rejection reason. Present when status=FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |                                                                                         |
| l2ApprovedTime           | string(int64)                      | false    | none        | L2 batch validation time. Present when status=SUCCESS_L2_APPROVED/FAILED_L2_REJECT_APPROVED |                                                                                         |
| createdTime              | string(int64)                      | false    | none        | Creation time                                                           |                                                                                         |
| updatedTime              | string(int64)                      | false    | none        | Update time                                                             |                                                                                         |

#### Enum Values

| Property | Value                    |
| -------- | ------------------------ |
| status   | UNKNOWN_DEPOSIT_STATUS  |
| status   | PENDING_CENSORING       |
| status   | SUCCESS_CENSOR_SUCCESS    |
| status   | SUCCESS_L2_APPROVED     |
| status   | FAILED_CENSOR_FAILURE    |
| status   | FAILED_L2_REJECT         |
| status   | FAILED_L2_REJECT_APPROVED |
| status   | UNRECOGNIZED             |


<a id="schemal2signature"></a>
### L2 signature information

| Name | Type   | Required | Constraints | Description        | Notes                  |
| ---- | ------ | -------- | ----------- | ------------------ | ---------------------- |
| r    | string | false    | none        |                    | BigInt as hex string   |
| s    | string | false    | none        |                    | BigInt as hex string   |
| v    | string | false    | none        |                    | BigInt as hex string   |


<a id="schemal1tx"></a>
### L1 transaction information

| Name        | Type            | Required | Constraints | Description       | Notes                     |
| ----------- | --------------- | -------- | ----------- | ----------------- | ------------------------- |
| hash        | string          | false    | none        | TX hash           |                           |
| index       | integer(int32)  | false    | none        | TX hash index     |                           |
| time        | string(int64)   | false    | none        | TX timestamp (milliseconds) |                     |
| blockHeight | string(int64)   | false    | none        | TX block height   |                           |


<a id="schemaresult<list<deposit>>"></a>
### Properties

| Name           | Type                        | Required | Constraints | Description     | Notes                                 |
| -------------- | --------------------------- | -------- | ----------- | --------------- | ------------------------------------- |
| code           | string                      | false    | none        |                 | Status code. "SUCCESS" if successful, otherwise failure |
| data           | [[Deposit](#schemadeposit)] | false    | none        |                 | Correct response data                 |
| errorParam     | object                      | false    | none        |                 | Parameter information in the error message |
| requestTime    | string(timestamp)           | false    | none        |                 | Server request receive time           |
| responseTime   | string(timestamp)           | false    | none        |                 | Server response return time           |
| traceId        | string                      | false    | none        |                 | Invocation trace ID                  |

<a id="schemaresult<createdeposit>"></a>
### Create deposit order Response

| Name           | Type                                   | Required | Constraints | Description     | Notes                                 |
| -------------- | -------------------------------------- | -------- | ----------- | --------------- | ------------------------------------- |
| code           | string                                 | false    | none        |                 | Status code. "SUCCESS" if successful, otherwise failure |
| data           | [CreateDeposit](#schemacreatedeposit) | false    | none        |                 | Create deposit order - response       |
| errorParam     | object                                 | false    | none        |                 | Parameter information in the error message |
| requestTime    | string(timestamp)                      | false    | none        |                 | Server request receive time           |
| responseTime   | string(timestamp)                      | false    | none        |                 | Server response return time           |
| traceId        | string                                 | false    | none        |                 | Invocation trace ID                  |

<a id="schemacreatedeposit"></a>
### Create deposit order Response Data

| Name      | Type          | Required | Constraints | Description     | Notes            |
| --------- | ------------- | -------- | ----------- | --------------- | ---------------- |
| depositId | string(int64) | false    | none        |                 | Deposit order ID |

<a id="schemacreatedepositparam"></a>
### Create deposit order Request

| Name            | Type           | Required | Constraints | Description                                                   | Notes                                |
| --------------- | -------------- | -------- | ----------- | ------------------------------------------------------------- | ------------------------------------ |
| accountId       | string(int64)  | false    | none        | Account ID                                                    |                                      |
| coinId          | string(int64)  | false    | none        | Coin ID                                                       |                                      |
| amount          | string(decimal)| false    | none        | Deposit amount                                                |                                      |
| ethAddress      | string         | false    | none        | Withdrawal address                                              |                                      |
| erc20Address    | string         | false    | none        | Withdrawal coin contract address                              |                                      |
| clientDepositId | string         | false    | none        | Client-defined ID for idempotency                              |                                      |
| l1Tx            | [L1Tx](#schemal1tx)          | false    | none        | L1 transaction information                                      |                                      |
| riskSignature   | string         | false    | none        | Risk control signature                                        |                                      |
| l2Key           | string         | false    | none        | L2 recipient account key                                        |                                      |
| extraType       | string         | false    | none        | Additional type for upper-layer business usage                    |                                      |
| extraDataJson   | string         | false    | none        | Extra data in JSON format, default is empty string              |                                      |


<a id="resultrequestrelayersignandbroadcast"></a>
### Create Relayer deposit order Response

| Name           | Type                                                  | Required | Constraints | Description     | Notes                                 |
| -------------- | ----------------------------------------------------- | -------- | ----------- | --------------- | ------------------------------------- |
| code           | string                                                | false    | none        |                 | Status code. "SUCCESS" if successful, otherwise failure |
| data           | [RequestRelayerSignAndBroadcast](#schemarequestrelayersignandbroadcast) | false    | none        |                 | Create Relayer deposit order - response |
| errorParam     | object                                                | false    | none        |                 | Parameter information in the error message |
| requestTime    | string(timestamp)                                     | false    | none        |                 | Server request receive time           |
| responseTime   | string(timestamp)                                     | false    | none        |                 | Server response return time           |
| traceId        | string                                                | false    | none        |                 | Invocation trace ID                  |

<a id="schemarequestrelayersignandbroadcast"></a>
### Create Relayer deposit order Response Data

| Name    | Type            | Required | Constraints | Description | Notes         |
| ------- | --------------- | -------- | ----------- | ----------- | ------------- |
| success | boolean(boolean) | false    | none        |             | Whether it's successful |

<a id="schemarequestrelayersignandbroadcastparam"></a>
### Create Relayer deposit order Request

| Name         |Type          | Required | Constraints | Description            | Notes                      |
| ------------ | ------------- | -------- | ----------- | ---------------------- | -------------------------- |
| deadline     | string(int64) | false    | none        | deadline               |                            |
| r            | string        | false    | none        | Client signature r      |                            |
| s            | string        | false    | none        | Client signature s      |                            |
| v            | string        | false    | none        | Client signature v      |                            |
| type         | string        | false    | none        | type                   |                            |
| amount       | string        | false    | none        | amount                 |                            |
| owner        | string        | false    | none        | owner                  |                            |
| starkKey     | string        | false    | none        | Stark key             |                            |
| positionId   | string(int64) | false    | none        | Position ID             |                            |
| chainId      | string(int64) | false    | none        | Chain ID              |                            |
| mpcSignature | string        | false    | none        | MPC signature          |                            |
