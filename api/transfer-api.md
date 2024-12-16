# TransferPrivateApi

<a id="opIdcreateTransferOut"></a>

## POST Create Transfer Out Order

POST /api/v1/private/transfer/createTransferOut

> Body Request Parameters

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "receiverAccountId": "string",
  "receiverL2Key": "string",
  "clientTransferId": "string",
  "transferReason": "UNKNOWN_TRANSFER_REASON",
  "l2Nonce": "string",
  "l2ExpireTime": "string",
  "l2Signature": "string",
  "extraType": "string",
  "extraDataJson": "string"
}
```

### Request Parameters

| Name | Location | Type | Required | Description |
|---|---|---|---|---|
| body | body | [CreateTransferOutParam](#schemacreatetransferoutparam) | No | none |

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

### Response Codes

| Status Code | Description | Notes | Schema |
|---|---|---|---|
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult) |

<a id="opIdgetTransferOutById"></a>

## GET Get Transfer Out Orders by ID

GET /api/v1/private/transfer/getTransferOutById

### Request Parameters

| Name | Location | Type | Required | Description |
|---|---|---|---|---|
| accountId | query | string | No | Account ID |
| transferOutIdList | query | string | No | Transfer out ID |

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
      "receiverAccountId": "string",
      "receiverL2Key": "string",
      "clientTransferId": "string",
      "isConditionTransfer": true,
      "conditionFactRegistryAddress": "string",
      "conditionFactErc20Address": "string",
      "conditionFactAmount": "string",
      "conditionFact": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_TRANSFER_STATUS",
      "receiverTransferInId": "string",
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

### Response Codes

| Status Code | Description | Notes | Schema |
|---|---|---|---|
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | Inline |

### Response Data Structure

<a id="opIdgetWithdrawAvailableAmount_1"></a>

## GET Get Available Withdrawal Amount

GET /api/v1/private/transfer/getTransferOutAvailableAmount

### Request Parameters

| Name | Location | Type | Required | Description |
|---|---|---|---|---|
| accountId | query | string | No | Account ID |
| coinId | query | string | No | Coin ID |

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

### Response Codes

| Status Code | Description | Notes | Schema |
|---|---|---|---|
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult) |

<a id="opIdgetTransferInById"></a>

## GET Get Transfer In Orders by ID

GET /api/v1/private/transfer/getTransferInById

### Request Parameters

| Name | Location | Type | Required | Description |
|---|---|---|---|---|
| accountId | query | string | No | Account ID |
| transferInIdList | query | string | No | Transfer In ID |

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
      "senderAccountId": "string",
      "senderL2Key": "string",
      "senderTransferOutId": "string",
      "clientTransferId": "string",
      "isConditionTransfer": true,
      "conditionFactRegistryAddress": "string",
      "conditionFactErc20Address": "string",
      "conditionFactAmount": "string",
      "conditionFact": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_TRANSFER_STATUS",
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

### Response Codes

| Status Code | Description | Notes | Schema |
|---|---|---|---|
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | Inline |

### Response Data Structure

<a id="opIdgetActiveTransferOut"></a>

## GET Get Paginated Transfer Out Orders

GET /api/v1/private/transfer/getActiveTransferOut

### Request Parameters

| Name | Location | Type | Required | Description |
|---|---|---|---|---|
| accountId | query | string | No | Account ID |
| size | query | string | No | Number of records per page. Must be greater than 0 and less than or equal to 100 |
| offsetData | query | string | No | Pagination offset. If empty or not provided, it retrieves the first page. |
| filterCoinIdList | query | string | No | Filter by coin IDs, if empty return all |
| filterStatusList | query | string | No | Filter by transfer status, if empty return all |
| filterTransferReasonList | query | string | No | Filter by transfer reason, if empty return all |
| filterStartCreatedTimeInclusive | query | string | No | Filter by start time (inclusive), if 0 it will return the earliest transfer in time |
| filterEndCreatedTimeExclusive | query | string | No | Filter by end time (exclusive), if 0 it will return the latest transfer in time |

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

### Response Codes

| Status Code | Description | Notes | Schema |
|---|---|---|---|
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult) |

<a id="opIdgetActiveTransferIn"></a>

## GET Get Paginated Transfer In Orders

GET /api/v1/private/transfer/getActiveTransferIn

### Request Parameters

| Name | Location | Type | Required | Description |
|---|---|---|---|---|
| accountId | query | string | No | Account ID |
| size | query | string | No | Number of records per page. Must be greater than 0 and less than or equal to 100 |
| offsetData | query | string | No | Pagination offset. If empty or not provided, it retrieves the first page. |
| filterCoinIdList | query | string | No | Filter by coin IDs, if empty return all |
| filterStatusList | query | string | No | Filter by transfer status, if empty return all |
| filterTransferReasonList | query | string | No | Filter by transfer reason, if empty return all |
| filterStartCreatedTimeInclusive | query | string | No | Filter by start time (inclusive), if 0 it will return the earliest transfer in time |
| filterEndCreatedTimeExclusive | query | string | No | Filter by end time (exclusive), if 0 it will return the latest transfer in time |

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
        "senderAccountId": "string",
        "senderL2Key": "string",
        "senderTransferOutId": "string",
        "clientTransferId": "string",
        "isConditionTransfer": true,
        "conditionFactRegistryAddress": "string",
        "conditionFactErc20Address": "string",
        "conditionFactAmount": "string",
        "conditionFact": "string",
        "transferReason": "UNKNOWN_TRANSFER_REASON",
        "extraType": "string",
        "extraDataJson": "string",
        "status": "UNKNOWN_TRANSFER_STATUS",
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

### Response Codes

| Status Code | Description | Notes | Schema |
|---|---|---|---|
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | Inline |

### Response Data Structure

# Data Models

<h2 id="tocS_Result<PageData<TransferIn>>">Result<PageData<TransferIn>></h2>

<a id="schemaresult<pagedata<transferin>>"></a>
<a id="schema_Result<PageData<TransferIn>>"></a>
<a id="tocSresult<pagedata<transferin>>"></a>
<a id="tocsresult<pagedata<transferin>>"></a>

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
        "senderAccountId": "string",
        "senderL2Key": "string",
        "senderTransferOutId": "string",
        "clientTransferId": "string",
        "isConditionTransfer": true,
        "conditionFactRegistryAddress": "string",
        "conditionFactErc20Address": "string",
        "conditionFactAmount": "string",
        "conditionFact": "string",
        "transferReason": "UNKNOWN_TRANSFER_REASON",
        "extraType": "string",
        "extraDataJson": "string",
        "status": "UNKNOWN_TRANSFER_STATUS",
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

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| code | string | false | none | Status code. "SUCCESS" for success, other values indicate failure. |
| data | [PageDataTransferIn](#schemapagedatatransferin) | false | none | Generic paginated response data |
| errorParam | object | false | none | Parameter information in error messages |
| » **additionalProperties** | string | false | none | Parameter information in error messages |
| requestTime | string(timestamp) | false | none | Server request receiving timestamp |
| responseTime | string(timestamp) | false | none | Server response returning timestamp |
| traceId | string | false | none | Call trace ID |

<h2 id="tocS_PageDataTransferIn">PageDataTransferIn</h2>

<a id="schemapagedatatransferin"></a>
<a id="schema_PageDataTransferIn"></a>
<a id="tocSpagedatatransferin"></a>
<a id="tocspagedatatransferin"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "amount": "string",
      "senderAccountId": "string",
      "senderL2Key": "string",
      "senderTransferOutId": "string",
      "clientTransferId": "string",
      "isConditionTransfer": true,
      "conditionFactRegistryAddress": "string",
      "conditionFactErc20Address": "string",
      "conditionFactAmount": "string",
      "conditionFact": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_TRANSFER_STATUS",
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
}
```

Generic paginated response data

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| dataList | [[TransferIn](#schematransferin)] | false | none | Data list |
| nextPageOffsetData | string | false | none | Offset to retrieve the next page. If no next page data, the value will be an empty string |

<h2 id="tocS_TransferIn">TransferIn</h2>

<a id="schematransferin"></a>
<a id="schema_TransferIn"></a>
<a id="tocStransferin"></a>
<a id="tocstransferin"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "senderAccountId": "string",
  "senderL2Key": "string",
  "senderTransferOutId": "string",
  "clientTransferId": "string",
  "isConditionTransfer": true,
  "conditionFactRegistryAddress": "string",
  "conditionFactErc20Address": "string",
  "conditionFactAmount": "string",
  "conditionFact": "string",
  "transferReason": "UNKNOWN_TRANSFER_REASON",
  "extraType": "string",
  "extraDataJson": "string",
  "status": "UNKNOWN_TRANSFER_STATUS",
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
```

Transfer In Order

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| id | string(int64) | false | none | Transfer In order ID |
| userId | string(int64) | false | none | User ID |
| accountId | string(int64) | false | none | Account ID |
| coinId | string(int64) | false | none | Coin ID |
| amount | string | false | none | Transfer amount |
| senderAccountId | string(int64) | false | none | Sender Account ID |
| senderL2Key | string | false | none | Sender account L2 key. bigint for hex str |
| senderTransferOutId | string(int64) | false | none | Sender transfer out order ID |
| clientTransferId | string | false | none | Client defined ID. Used for idempotent checks and signature generation nonce |
| isConditionTransfer | boolean | false | none | Whether it is a conditional transfer |
| conditionFactRegistryAddress | string | false | none | Address of condition fact registry contract. Required when is_condition_transfer=true |
| conditionFactErc20Address | string | false | none | ERC20 address used to generate the condition fact. Required when is_conditional_transfer=true |
| conditionFactAmount | string | false | none | Amount used to generate condition fact. Required when is_conditional_transfer=true. |
| conditionFact | string | false | none | The conditional transfer fact. Required when is_condition_transfer=true |
| transferReason | string | false | none | Transfer reason |
| extraType | string | false | none | Additional type. Used by upper layer business |
| extraDataJson | string | false | none | Additional data in JSON format. Defaults to empty string |
| status | string | false | none | Transfer status |
| collateralTransactionId | string(int64) | false | none | ID of related collateral detail. Exists when status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |
| censorTxId | string(int64) | false | none | Censor processing sequence. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |
| censorTime | string(int64) | false | none | Censor processing time. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |
| censorFailCode | string | false | none | Censor failure error code. Exists when status=FAILED_CENSOR_FAILURE |
| censorFailReason | string | false | none | Censor failure reason. Exists when status=FAILED_CENSOR_FAILURE |
| l2TxId | string(int64) | false | none | L2 push transaction ID. Exists when censor_status=CENSOR_SUCCESS/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED |
| l2RejectTime | string(int64) | false | none | L2 rejection time. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED |
| l2RejectCode | string | false | none | L2 rejection error code. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED |
| l2RejectReason | string | false | none | L2 rejection reason. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED |
| l2ApprovedTime | string(int64) | false | none | L2 batch verification time. Exists when status=L2_APPROVED/L2_REJECT_APPROVED |
| createdTime | string(int64) | false | none | Creation time |
| updatedTime | string(int64) | false | none | Update time |

#### Enum Values

| Property | Value |
|---|---|
| transferReason | UNKNOWN_TRANSFER_REASON |
| transferReason | USER_TRANSFER |
| transferReason | FAST_WITHDRAW |
| transferReason | CROSS_DEPOSIT |
| transferReason | CROSS_WITHDRAW |
| transferReason | UNRECOGNIZED |
| status | UNKNOWN_TRANSFER_STATUS |
| status | PENDING_CHECKING |
| status | PENDING_CENSORING |
| status | SUCCESS_CENSOR_SUCCESS |
| status | SUCCESS_L2_APPROVED |
| status | FAILED_CHECK_INVALID |
| status | FAILED_CENSOR_FAILURE |
| status | FAILED_L2_REJECT |
| status | FAILED_L2_REJECT_APPROVED |
| status | UNRECOGNIZED |

<h2 id="tocS_Result<PageData<TransferOut>>">Result<PageData<TransferOut>></h2>

<a id="schemaresult<pagedata<transferout>>"></a>
<a id="schema_Result<PageData<TransferOut>>"></a>
<a id="tocSresult<pagedata<transferout>>"></a>
<a id="tocsresult<pagedata<transferout>>"></a>

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
        "receiverAccountId": "string",
        "receiverL2Key": "string",
        "clientTransferId": "string",
        "isConditionTransfer": true,
        "conditionFactRegistryAddress": "string",
        "conditionFactErc20Address": "string",
        "conditionFactAmount": "string",
        "conditionFact": "string",
        "transferReason": "UNKNOWN_TRANSFER_REASON",
        "l2Nonce": "string",
        "l2ExpireTime": "string",
        "l2Signature": {
          "r": "string",
          "s": "string",
          "v": "string"
        },
        "extraType": "string",
        "extraDataJson": "string",
        "status": "UNKNOWN_TRANSFER_STATUS",
        "receiverTransferInId": "string",
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

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| code | string | false | none | Status code. "SUCCESS" for success, other values indicate failure. |
| data | [PageDataTransferOut](#schemapagedatatransferout) | false | none | Generic paginated response data |
| errorParam | object | false | none | Parameter information in error messages |
| » **additionalProperties** | string | false | none | Parameter information in error messages |
| requestTime | string(timestamp) | false | none | Server request receiving timestamp |
| responseTime | string(timestamp) | false | none | Server response returning timestamp |
| traceId | string | false | none | Call trace ID |

<h2 id="tocS_PageDataTransferOut">PageDataTransferOut</h2>

<a id="schemapagedatatransferout"></a>
<a id="schema_PageDataTransferOut"></a>
<a id="tocSpagedatatransferout"></a>
<a id="tocspagedatatransferout"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "amount": "string",
      "receiverAccountId": "string",
      "receiverL2Key": "string",
      "clientTransferId": "string",
      "isConditionTransfer": true,
      "conditionFactRegistryAddress": "string",
      "conditionFactErc20Address": "string",
      "conditionFactAmount": "string",
      "conditionFact": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_TRANSFER_STATUS",
      "receiverTransferInId": "string",
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
}
```

Generic paginated response data

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| dataList | [[TransferOut](#schematransferout)] | false | none | Data list |
| nextPageOffsetData | string | false | none | Offset to retrieve the next page. If no next page data, the value will be an empty string |

<h2 id="tocS_TransferOut">TransferOut</h2>

<a id="schematransferout"></a>
<a id="schema_TransferOut"></a>
<a id="tocStransferout"></a>
<a id="tocstransferout"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "receiverAccountId": "string",
  "receiverL2Key": "string",
  "clientTransferId": "string",
  "isConditionTransfer": true,
  "conditionFactRegistryAddress": "string",
  "conditionFactErc20Address": "string",
  "conditionFactAmount": "string",
  "conditionFact": "string",
  "transferReason": "UNKNOWN_TRANSFER_REASON",
  "l2Nonce": "string",
  "l2ExpireTime": "string",
  "l2Signature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "extraType": "string",
  "extraDataJson": "string",
  "status": "UNKNOWN_TRANSFER_STATUS",
  "receiverTransferInId": "string",
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
```

Transfer Out Order

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| id | string(int64) | false | none | Transfer out order ID |
| userId | string(int64) | false | none | User ID |
| accountId | string(int64) | false | none | Account ID |
| coinId | string(int64) | false | none | Coin ID |
| amount | string | false | none | Transfer amount |
| receiverAccountId | string(int64) | false | none | Receiver Account ID |
| receiverL2Key | string | false | none | Receiver account L2 key. bigint for hex str |
| clientTransferId | string | false | none | Client defined ID. Used for idempotent checks and signature generation nonce |
| isConditionTransfer | boolean | false | none | Whether it is a conditional transfer |
| conditionFactRegistryAddress | string | false | none | Address of condition fact registry contract. Required when is_conditional_transfer=true |
| conditionFactErc20Address | string | false | none | ERC20 address used to generate the condition fact. Required when is_conditional_transfer=true |
| conditionFactAmount | string | false | none | Amount used to generate condition fact. Required when is_conditional_transfer=true. |
| conditionFact | string | false | none | The conditional transfer fact. Required when is_conditional_transfer=true |
| transferReason | string | false | none | Transfer reason |
| l2Nonce | string(int64) | false | none | L2 signature nonce. Take the first 32 bits of sha256(client_transfer_id) |
| l2ExpireTime | string(int64) | false | none | L2 signature expiration time in milliseconds. When generating/verifying the signature, the hour should be used: l2_expire_time / 3600000 |
| l2Signature | [L2Signature](#schemal2signature) | false | none | L2 signature information |
| extraType | string | false | none | Additional type. Used by upper layer business |
| extraDataJson | string | false | none | Additional data in JSON format. Defaults to empty string |
| status | string | false | none | Transfer status |
| receiverTransferInId | string(int64) | false | none | ID of receiver transfer in order. |
| collateralTransactionId | string(int64) | false | none | ID of related collateral detail. Exists when status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |
| censorTxId | string(int64) | false | none | Censor processing sequence. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |
| censorTime | string(int64) | false | none | Censor processing time. Exists when status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED |
| censorFailCode | string | false | none | Censor failure error code. Exists when status=FAILED_CENSOR_FAILURE |
| censorFailReason | string | false | none | Censor failure reason. Exists when status=FAILED_CENSOR_FAILURE |
| l2TxId | string(int64) | false | none | L2 push transaction ID. Exists when censor_status=CENSOR_SUCCESS/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED |
| l2RejectTime | string(int64) | false | none | L2 rejection time. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED |
| l2RejectCode | string | false | none | L2 rejection error code. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED |
| l2RejectReason | string | false | none | L2 rejection reason. Exists when censor_status=L2_REJECT/L2_REJECT_APPROVED |
| l2ApprovedTime | string(int64) | false | none | L2 batch verification time. Exists when status=L2_APPROVED/L2_REJECT_APPROVED |
| createdTime | string(int64) | false | none | Creation time |
| updatedTime | string(int64) | false | none | Update time |

#### Enum Values

| Property | Value |
|---|---|
| transferReason | UNKNOWN_TRANSFER_REASON |
| transferReason | USER_TRANSFER |
| transferReason | FAST_WITHDRAW |
| transferReason | CROSS_DEPOSIT |
| transferReason | CROSS_WITHDRAW |
| transferReason | UNRECOGNIZED |
| status | UNKNOWN_TRANSFER_STATUS |
| status | PENDING_CHECKING |
| status | PENDING_CENSORING |
| status | SUCCESS_CENSOR_SUCCESS |
| status | SUCCESS_L2_APPROVED |
| status | FAILED_CHECK_INVALID |
| status | FAILED_CENSOR_FAILURE |
| status | FAILED_L2_REJECT |
| status | FAILED_L2_REJECT_APPROVED |
| status | UNRECOGNIZED |

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

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| r | string | false | none | bigint for hex str |
| s | string | false | none | bigint for hex str |
| v | string | false | none | bigint for hex str |

<h2 id="tocS_Result<List<TransferIn>>">Result<List<TransferIn>></h2>

<a id="schemaresult<list<transferin>>"></a>
<a id="schema_Result<List<TransferIn>>"></a>
<a id="tocSresult<list<transferin>>"></a>
<a id="tocsresult<list<transferin>>"></a>

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
      "senderAccountId": "string",
      "senderL2Key": "string",
      "senderTransferOutId": "string",
      "clientTransferId": "string",
      "isConditionTransfer": true,
      "conditionFactRegistryAddress": "string",
      "conditionFactErc20Address": "string",
      "conditionFactAmount": "string",
      "conditionFact": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_TRANSFER_STATUS",
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

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| code | string | false | none | Status code. "SUCCESS" for success, other values indicate failure. |
| data | [[TransferIn](#schematransferin)] | false | none | Correct response data |
| errorParam | object | false | none | Parameter information in error messages |
| » **additionalProperties** | string | false | none | Parameter information in error messages |
| requestTime | string(timestamp) | false | none | Server request receiving timestamp |
| responseTime | string(timestamp) | false | none | Server response returning timestamp |
| traceId | string | false | none | Call trace ID |

<h2 id="tocS_Result<GetTransferOutAvailableAmount>">Result<GetTransferOutAvailableAmount></h2>

<a id="schemaresult<gettransferoutavailableamount>"></a>
<a id="schema_Result<GetTransferOutAvailableAmount>"></a>
<a id="tocSresult<gettransferoutavailableamount>"></a>
<a id="tocsresult<gettransferoutavailableamount>"></a>

```json
{
  "code": "string",
  "data": {
    "availableAmount": "string"
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

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| code | string | false | none | Status code. "SUCCESS" for success, other values indicate failure. |
| data | [GetTransferAvailableAmount](#schemagettransferavailableamount) | false | none | Get Transfer Available Amount - Response |
| errorParam | object | false | none | Parameter information in error messages |
| » **additionalProperties** | string | false | none | Parameter information in error messages |
| requestTime | string(timestamp) | false | none | Server request receiving timestamp |
| responseTime | string(timestamp) | false | none | Server response returning timestamp |
| traceId | string | false | none | Call trace ID |

<h2 id="tocS_GetTransferAvailableAmount">GetTransferAvailableAmount</h2>

<a id="schemagettransferavailableamount"></a>
<a id="schema_GetTransferAvailableAmount"></a>
<a id="tocSgettransferavailableamount"></a>
<a id="tocsgettransferavailableamount"></a>

```json
{
  "availableAmount": "string"
}
```

Get Transfer Available Amount - Response

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| availableAmount | string(decimal) | false | none | Available amount |

<h2 id="tocS_Result<List<TransferOut>>">Result<List<TransferOut>></h2>

<a id="schemaresult<list<transferout>>"></a>
<a id="schema_Result<List<TransferOut>>"></a>
<a id="tocSresult<list<transferout>>"></a>
<a id="tocsresult<list<transferout>>"></a>

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
      "receiverAccountId": "string",
      "receiverL2Key": "string",
      "clientTransferId": "string",
      "isConditionTransfer": true,
      "conditionFactRegistryAddress": "string",
      "conditionFactErc20Address": "string",
      "conditionFactAmount": "string",
      "conditionFact": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "l2Nonce": "string",
      "l2ExpireTime": "string",
      "l2Signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_TRANSFER_STATUS",
      "receiverTransferInId": "string",
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

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| code | string | false | none | Status code. "SUCCESS" for success, other values indicate failure. |
| data | [[TransferOut](#schematransferout)] | false | none | Correct response data |
| errorParam | object | false | none | Parameter information in error messages |
| » **additionalProperties** | string | false | none | Parameter information in error messages |
| requestTime | string(timestamp) | false | none | Server request receiving timestamp |
| responseTime | string(timestamp) | false | none | Server response returning timestamp |
| traceId | string | false | none | Call trace ID |

<h2 id="tocS_Result<CreateTransferOut>">Result<CreateTransferOut></h2>

<a id="schemaresult<createtransferout>"></a>
<a id="schema_Result<CreateTransferOut>"></a>
<a id="tocSresult<createtransferout>"></a>
<a id="tocsresult<createtransferout>"></a>

```json
{
  "code": "string",
  "data": {
    "transferOutId": "string"
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

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| code | string | false | none | Status code. "SUCCESS" for success, other values indicate failure. |
| data | [CreateTransferOut](#schemacreatetransferout) | false | none | Create Transfer Out Order - Response |
| errorParam | object | false | none | Parameter information in error messages |
| » **additionalProperties** | string | false | none | Parameter information in error messages |
| requestTime | string(timestamp) | false | none | Server request receiving timestamp |
| responseTime | string(timestamp) | false | none | Server response returning timestamp |
| traceId | string | false | none | Call trace ID |

<h2 id="tocS_CreateTransferOut">CreateTransferOut</h2>

<a id="schemacreatetransferout"></a>
<a id="schema_CreateTransferOut"></a>
<a id="tocScreatetransferout"></a>
<a id="tocscreatetransferout"></a>

```json
{
  "transferOutId": "string"
}
```

Create Transfer Out Order - Response

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| transferOutId | string(int64) | false | none | Transfer out order ID |

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

Generic response structure

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| code | string | false | none | Status code. "SUCCESS" for success, other values indicate failure. |
| msg | string | false | none | Detailed error message if an error occurs |
| requestTime | string(int64) | false | none | Server request receiving timestamp |
| responseTime | string(int64) | false | none | Server response returning timestamp |

<h2 id="tocS_CreateTransferOutParam">CreateTransferOutParam</h2>

<a id="schemacreatetransferoutparam"></a>
<a id="schema_CreateTransferOutParam"></a>
<a id="tocScreatetransferoutparam"></a>
<a id="tocscreatetransferoutparam"></a>

```json
{
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "receiverAccountId": "string",
  "receiverL2Key": "string",
  "clientTransferId": "string",
  "transferReason": "UNKNOWN_TRANSFER_REASON",
  "l2Nonce": "string",
  "l2ExpireTime": "string",
  "l2Signature": "string",
  "extraType": "string",
  "extraDataJson": "string"
}
```

Create Transfer Out Order request parameters

### Properties

| Name | Type | Required | Constraints | Description |
|---|---|---|---|---|
| accountId | string(int64) | false | none | Account ID |
| coinId | string(int64) | false | none | Asset ID |
| amount | string | false | none | Transfer amount |
| receiverAccountId | string | false | none | Receiver account ID |
| receiverL2Key | string | false | none | Receiver account L2 key. bigint for hex str |
| clientTransferId | string | false | none | Client defined ID. Used for idempotent checks and signature generation nonce |
| transferReason | string | false | none | Transfer reason |
| l2Nonce | string(int64) | false | none | L2 signature nonce. Take the first 32 bits of sha256(client_withdraw_id) |
| l2ExpireTime | string(int64) | false | none | L2 signature expiration time in milliseconds. When generating/verifying the signature, the hour should be used: l2_expire_time / 3600000 |
| l2Signature | string | false | none | L2 signature |
| extraType | string | false | none | Additional type. Used by upper layer business |
| extraDataJson | string | false | none | Additional data in JSON format. Defaults to empty string |

#### Enum Values

| Property | Value |
|---|---|
| transferReason | UNKNOWN_TRANSFER_REASON |
| transferReason | USER_TRANSFER |
| transferReason | FAST_WITHDRAW |
| transferReason | CROSS_DEPOSIT |
| transferReason | CROSS_WITHDRAW |
| transferReason | UNRECOGNIZED |
