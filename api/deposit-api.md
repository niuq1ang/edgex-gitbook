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

# 05.DepositPrivateApi

<a id="opIdrequestRelayerSignAndBroadcast"></a>

## POST 创建 Relayer 充值单

POST /api/v1/private/deposit/requestRelayerSignAndBroadcast

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[RequestRelayerSignAndBroadcastParam](#schemarequestrelayersignandbroadcastparam)| 否 |none|

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

<a id="opIdcreateDeposit"></a>

## POST 创建充值单

POST /api/v1/private/deposit/createDeposit

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateDepositParam](#schemacreatedepositparam)| 否 |none|

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

<a id="opIdgetDepositById"></a>

## GET 根据充值单id批量获取充值单

GET /api/v1/private/deposit/getDepositById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|depositIdList|query|string| 否 |充值单id|

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

<a id="opIdgetDepositByClientDepositId"></a>

## GET 根据账户id和充值单clientId批量获取充值单

GET /api/v1/private/deposit/getDepositByClientDepositId

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|clientDepositIdList|query|string| 否 |客户自定义id|

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

<a id="opIdgetActiveDeposit"></a>

## GET 翻页获取充值单

GET /api/v1/private/deposit/getActiveDeposit

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

# 数据模型

<h2 id="tocS_Result<PageData<Deposit>>">Result<PageData<Deposit>></h2>

<a id="schemaresult<pagedata<deposit>>"></a>
<a id="schema_Result<PageData<Deposit>>"></a>
<a id="tocSresult<pagedata<deposit>>"></a>
<a id="tocsresult<pagedata<deposit>>"></a>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[PageDataDeposit](#schemapagedatadeposit)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataDeposit">PageDataDeposit</h2>

<a id="schemapagedatadeposit"></a>
<a id="schema_PageDataDeposit"></a>
<a id="tocSpagedatadeposit"></a>
<a id="tocspagedatadeposit"></a>

```json
{
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
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[Deposit](#schemadeposit)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Deposit">Deposit</h2>

<a id="schemadeposit"></a>
<a id="schema_Deposit"></a>
<a id="tocSdeposit"></a>
<a id="tocsdeposit"></a>

```json
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

```

充值单

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||充值单id|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|amount|string|false|none||充值数量|
|ethAddress|string|false|none||充值的eth地址，可能与账户里的eth地址不一样|
|erc20Address|string|false|none||充值的币种合约地址|
|clientDepositId|string|false|none||客户自定义id，用于幂等校验|
|l1Tx|[L1Tx](#schemal1tx)|false|none||L1交易信息|
|riskSignature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|l2Key|string|false|none||L2上的收款账户key|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|status|string|false|none||充值单状态|
|collateralTransactionId|string(int64)|false|none||关联的抵押品明细id。当 status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|censorTxId|string(int64)|false|none||审查处理序号。当 status=SUCCESS_XXX/FAILED_XXX 时存在|
|censorTime|string(int64)|false|none||审查处理时间。当 status=SUCCESS_XXX/FAILED_XXX|
|censorFailCode|string|false|none||审查失败错误码。当 status=FAILED_CENSOR_FAILURE 时存在|
|censorFailReason|string|false|none||审查失败原因。当 status=FAILED_CENSOR_FAILURE 时存在|
|l2TxId|string(int64)|false|none||l2推送交易id。当 status=SUCCESS_XXX/FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|l2RejectTime|string(int64)|false|none||l2拒绝时间。当 status=FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|l2RejectCode|string|false|none||l2拒绝错误码。当 status=FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|l2RejectReason|string|false|none||l2拒绝原因。当 status=FAILED_L2_REJECT/FAILED_L2_REJECT_APPROVED 时存在|
|l2ApprovedTime|string(int64)|false|none||l2批次验证时间。当 status=SUCCESS_L2_APPROVED/FAILED_L2_REJECT_APPROVED 时存在|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|status|UNKNOWN_DEPOSIT_STATUS|
|status|PENDING_CENSORING|
|status|SUCCESS_CENSOR_SUCCESS|
|status|SUCCESS_L2_APPROVED|
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

L1交易信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|hash|string|false|none||tx hash|
|index|integer(int32)|false|none||tx hash 所属index|
|time|string(int64)|false|none||tx 链上时间戳，单位毫秒|
|blockHeight|string(int64)|false|none||tx所在区块高度|

<h2 id="tocS_Result<List<Deposit>>">Result<List<Deposit>></h2>

<a id="schemaresult<list<deposit>>"></a>
<a id="schema_Result<List<Deposit>>"></a>
<a id="tocSresult<list<deposit>>"></a>
<a id="tocsresult<list<deposit>>"></a>

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
|data|[[Deposit](#schemadeposit)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Result<CreateDeposit>">Result<CreateDeposit></h2>

<a id="schemaresult<createdeposit>"></a>
<a id="schema_Result<CreateDeposit>"></a>
<a id="tocSresult<createdeposit>"></a>
<a id="tocsresult<createdeposit>"></a>

```json
{
  "code": "string",
  "data": {
    "depositId": "string"
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
|data|[CreateDeposit](#schemacreatedeposit)|false|none||创建充值单-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CreateDeposit">CreateDeposit</h2>

<a id="schemacreatedeposit"></a>
<a id="schema_CreateDeposit"></a>
<a id="tocScreatedeposit"></a>
<a id="tocscreatedeposit"></a>

```json
{
  "depositId": "string"
}

```

创建充值单-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|depositId|string(int64)|false|none||充值单id|

<h2 id="tocS_CreateDepositParam">CreateDepositParam</h2>

<a id="schemacreatedepositparam"></a>
<a id="schema_CreateDepositParam"></a>
<a id="tocScreatedepositparam"></a>
<a id="tocscreatedepositparam"></a>

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

创建充值单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||货币id|
|amount|string(decimal)|false|none||充值数量|
|ethAddress|string|false|none||提现到的地址。|
|erc20Address|string|false|none||提现的币种合约地址|
|clientDepositId|string|false|none||客户自定义id，用于幂等校验|
|l1Tx|[L1Tx](#schemal1tx)|false|none||L1交易信息|
|riskSignature|string|false|none||风控签名|
|l2Key|string|false|none||L2上的收款账户key|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|

<h2 id="tocS_Result<ResultRequestRelayerSignAndBroadcast>">Result<ResultRequestRelayerSignAndBroadcast></h2>

<a id="schemaresult<resultrequestrelayersignandbroadcast>"></a>
<a id="schema_Result<ResultRequestRelayerSignAndBroadcast>"></a>
<a id="tocSresult<resultrequestrelayersignandbroadcast>"></a>
<a id="tocsresult<resultrequestrelayersignandbroadcast>"></a>

```json
{
  "code": "string",
  "data": {
    "success": true
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
|data|[RequestRelayerSignAndBroadcast](#schemarequestrelayersignandbroadcast)|false|none||创建 Relayer 充值单-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_RequestRelayerSignAndBroadcast">RequestRelayerSignAndBroadcast</h2>

<a id="schemarequestrelayersignandbroadcast"></a>
<a id="schema_RequestRelayerSignAndBroadcast"></a>
<a id="tocSrequestrelayersignandbroadcast"></a>
<a id="tocsrequestrelayersignandbroadcast"></a>

```json
{
  "success": true
}

```

创建 Relayer 充值单-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|success|boolean(boolean)|false|none||是否成功|

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

<h2 id="tocS_RequestRelayerSignAndBroadcastParam">RequestRelayerSignAndBroadcastParam</h2>

<a id="schemarequestrelayersignandbroadcastparam"></a>
<a id="schema_RequestRelayerSignAndBroadcastParam"></a>
<a id="tocSrequestrelayersignandbroadcastparam"></a>
<a id="tocsrequestrelayersignandbroadcastparam"></a>

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

创建 Relayer 充值单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|deadline|string(int64)|false|none||deadline|
|r|string|false|none||client signature r|
|s|string|false|none||client signature s|
|v|string|false|none||client signature v|
|type|string|false|none||type|
|amount|string|false|none||amount|
|owner|string|false|none||owner|
|starkKey|string|false|none||stark key|
|positionId|string(int64)|false|none||position id|
|chainId|string(int64)|false|none||chain id|
|mpcSignature|string|false|none||mpc signature|

