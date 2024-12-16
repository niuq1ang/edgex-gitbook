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

# 07.TransferPrivateApi

<a id="opIdcreateTransferOut"></a>

## POST 创建委托单

POST /api/v1/private/transfer/createTransferOut

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateTransferOutParam](#schemacreatetransferoutparam)| 否 |none|

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

<a id="opIdgetTransferOutById"></a>

## GET 根据充值单id批量获取转出单

GET /api/v1/private/transfer/getTransferOutById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|transferOutIdList|query|string| 否 |转出单id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetWithdrawAvailableAmount_1"></a>

## GET 翻页获取提现单

GET /api/v1/private/transfer/getTransferOutAvailableAmount

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|coinId|query|string| 否 |币id|

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

<a id="opIdgetTransferInById"></a>

## GET 根据充值单id批量获取转入单

GET /api/v1/private/transfer/getTransferInById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|transferInIdList|query|string| 否 |转入单id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetActiveTransferOut"></a>

## GET 翻页获取转出单

GET /api/v1/private/transfer/getActiveTransferOut

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的转入单，如果为空则获取所有抵押品coinId的转入单|
|filterStatusList|query|string| 否 |过滤获取指定状态的转入单，不填的话所有状态转入单|
|filterTransferReasonList|query|string| 否 |过滤获取指定转账原因的转入单，不填的话所有转账原因转入单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的转入单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 |过滤获取指定结束时间创建的转入单 (不包含)，不填或者为0的话就到最近|

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

<a id="opIdgetActiveTransferIn"></a>

## GET 翻页获取转入单

GET /api/v1/private/transfer/getActiveTransferIn

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的转出单，如果为空则获取所有抵押品coinId的转入单|
|filterStatusList|query|string| 否 |过滤获取指定状态的转入单，不填的话所有状态转出单|
|filterTransferReasonList|query|string| 否 |过滤获取指定转账原因的转入单，不填的话所有转账原因转出单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的转出单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 |过滤获取指定结束时间创建的转出单 (不包含)，不填或者为0的话就到最近|

> 返回示例

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

# 数据模型

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[PageDataTransferIn](#schemapagedatatransferin)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[TransferIn](#schematransferin)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

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

转账转入单

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||转账转出单id|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|amount|string|false|none||转账数量|
|senderAccountId|string(int64)|false|none||发款方账户id|
|senderL2Key|string|false|none||发款方账户L2 key. bigint for hex str|
|senderTransferOutId|string(int64)|false|none||发款方转账转出单id|
|clientTransferId|string|false|none||客户自定义id，用于幂等校验和生成签名nonce|
|isConditionTransfer|boolean|false|none||是否为条件转账|
|conditionFactRegistryAddress|string|false|none||条件转账 fact注册合约地址，当is_condition_transfer=true时必填。|
|conditionFactErc20Address|string|false|none||条件转账fact生成所使用的erc20地址，当is_conditional_transfer=true时必填。|
|conditionFactAmount|string|false|none||条件转账fact生成所使用的amount，当is_conditional_transfer=true时必填。|
|conditionFact|string|false|none||条件转账 fact，当is_condition_transfer=true时必填。|
|transferReason|string|false|none||转账原因|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|status|string|false|none||转账状态|
|collateralTransactionId|string(int64)|false|none||关联的抵押品明细id。当 status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|censorTxId|string(int64)|false|none||审查处理序号。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|censorTime|string(int64)|false|none||审查处理时间。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|censorFailCode|string|false|none||审查失败错误码。当 status=FAILED_CENSOR_FAILURE 时存在|
|censorFailReason|string|false|none||审查失败原因。当 status=FAILED_CENSOR_FAILURE 时存在|
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
|transferReason|UNKNOWN_TRANSFER_REASON|
|transferReason|USER_TRANSFER|
|transferReason|FAST_WITHDRAW|
|transferReason|CROSS_DEPOSIT|
|transferReason|CROSS_WITHDRAW|
|transferReason|UNRECOGNIZED|
|status|UNKNOWN_TRANSFER_STATUS|
|status|PENDING_CHECKING|
|status|PENDING_CENSORING|
|status|SUCCESS_CENSOR_SUCCESS|
|status|SUCCESS_L2_APPROVED|
|status|FAILED_CHECK_INVALID|
|status|FAILED_CENSOR_FAILURE|
|status|FAILED_L2_REJECT|
|status|FAILED_L2_REJECT_APPROVED|
|status|UNRECOGNIZED|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[PageDataTransferOut](#schemapagedatatransferout)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[TransferOut](#schematransferout)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

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

转账转出单

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||转账转出单id|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|amount|string|false|none||转账数量|
|receiverAccountId|string(int64)|false|none||收款账户id|
|receiverL2Key|string|false|none||收款账户L2 key. bigint for hex str|
|clientTransferId|string|false|none||客户自定义id，用于幂等校验和生成签名nonce|
|isConditionTransfer|boolean|false|none||是否为条件转账|
|conditionFactRegistryAddress|string|false|none||条件转账 fact注册合约地址，当is_conditional_transfer=true时必填。|
|conditionFactErc20Address|string|false|none||条件转账fact生成所使用的erc20地址，当is_conditional_transfer=true时必填。|
|conditionFactAmount|string|false|none||条件转账fact生成所使用的amount，当is_conditional_transfer=true时必填。|
|conditionFact|string|false|none||条件转账 fact，当is_conditional_transfer=true时必填。|
|transferReason|string|false|none||转账原因|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_transfer_id) 前32个bit|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间，单位毫秒。参与签名生成/校验时要取小时数，即 l2_expire_time / 3600000|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|status|string|false|none||转账状态|
|receiverTransferInId|string(int64)|false|none||收款方转账转入单id|
|collateralTransactionId|string(int64)|false|none||关联的抵押品明细id。当 status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|censorTxId|string(int64)|false|none||审查处理序号。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|censorTime|string(int64)|false|none||审查处理时间。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|censorFailCode|string|false|none||审查失败错误码。当 status=FAILED_CENSOR_FAILURE 时存在|
|censorFailReason|string|false|none||审查失败原因。当 status=FAILED_CENSOR_FAILURE 时存在|
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
|transferReason|UNKNOWN_TRANSFER_REASON|
|transferReason|USER_TRANSFER|
|transferReason|FAST_WITHDRAW|
|transferReason|CROSS_DEPOSIT|
|transferReason|CROSS_WITHDRAW|
|transferReason|UNRECOGNIZED|
|status|UNKNOWN_TRANSFER_STATUS|
|status|PENDING_CHECKING|
|status|PENDING_CENSORING|
|status|SUCCESS_CENSOR_SUCCESS|
|status|SUCCESS_L2_APPROVED|
|status|FAILED_CHECK_INVALID|
|status|FAILED_CENSOR_FAILURE|
|status|FAILED_L2_REJECT|
|status|FAILED_L2_REJECT_APPROVED|
|status|UNRECOGNIZED|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[TransferIn](#schematransferin)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[GetTransferAvailableAmount](#schemagettransferavailableamount)|false|none||获取转账可用数量-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

获取转账可用数量-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|availableAmount|string(decimal)|false|none||可用数量|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[TransferOut](#schematransferout)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[CreateTransferOut](#schemacreatetransferout)|false|none||创建转出单-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

创建转出单-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|transferOutId|string(int64)|false|none||转出单id|

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

创建转出单请求参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||充提资产id|
|amount|string|false|none||转账数量|
|receiverAccountId|string|false|none||收款账户id|
|receiverL2Key|string|false|none||收款账户L2 key. bigint for hex str|
|clientTransferId|string|false|none||客户自定义id，用于幂等校验和生成签名nonce|
|transferReason|string|false|none||转账原因|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_withdraw_id) 前32个bit|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间，单位毫秒。参与签名生成/校验时要取小时数，即 l2_expire_time / 3600000|
|l2Signature|string|false|none||提交l2的签名|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||附加数据，json格式，默认为空串|

#### 枚举值

|属性|值|
|---|---|
|transferReason|UNKNOWN_TRANSFER_REASON|
|transferReason|USER_TRANSFER|
|transferReason|FAST_WITHDRAW|
|transferReason|CROSS_DEPOSIT|
|transferReason|CROSS_WITHDRAW|
|transferReason|UNRECOGNIZED|

