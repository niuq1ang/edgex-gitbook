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

# 09.AssetsPrivateApi

<a id="opIdcreateNormalWithdraw"></a>

## POST 创建普通提现单

POST /api/v1/private/assets/createNormalWithdraw

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateNormalWithdrawParam](#schemacreatenormalwithdrawparam)| 否 |none|

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

<a id="opIdcreateFastWithdraw"></a>

## POST 创建快速提现单

POST /api/v1/private/assets/createFastWithdraw

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateFastWithdrawRequest](#schemacreatefastwithdrawrequest)| 否 |none|

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

<a id="opIdcreateCrossWithdraw"></a>

## POST 创建快速提现单

POST /api/v1/private/assets/createCrossWithdraw

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateCrossWithdrawParam](#schemacreatecrosswithdrawparam)| 否 |none|

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

<a id="opIdgetNormalWithdrawableAmount"></a>

## GET 查询用户普通提现可提金额

GET /api/v1/private/assets/getNormalWithdrawableAmount

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|address|query|string| 是 |用户地址|

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

<a id="opIdgetNormalWithdrawById"></a>

## GET 根据账户id和提现单id批量获取普通提现单

GET /api/v1/private/assets/getNormalWithdrawById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|normalWithdrawIdList|query|string| 否 |提现单id|

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

<a id="opIdgetFastWithdrawSignInfo"></a>

## GET 查询快速提现签名需要的信息

GET /api/v1/private/assets/getFastWithdrawSignInfo

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|chainId|query|string| 否 |哪条链|
|amount|query|string| 否 |提现金额|

> 返回示例

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetFastWithdrawById"></a>

## GET 根据账户id和提现单id批量获取快速提现单

GET /api/v1/private/assets/getFastWithdrawById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|fastWithdrawIdList|query|string| 否 |提现单id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetCrossWithdrawSignInfo"></a>

## GET 查询跨链提现签名需要的信息

GET /api/v1/private/assets/getCrossWithdrawSignInfo

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|chainId|query|string| 否 |链id|
|amount|query|string| 否 |提现金额|

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

<a id="opIdgetCrossWithdrawById"></a>

## GET 根据账户id和提现单id批量获取跨链提现单

GET /api/v1/private/assets/getCrossWithdrawById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|crossWithdrawIdList|query|string| 否 |提现单id|

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

<a id="opIdgetCoinRate"></a>

## GET 聚合查询所有充提币订单记录

GET /api/v1/private/assets/getCoinRate

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|chainId|query|string| 否 |链id|
|coin|query|string| 否 |币种|

> 返回示例

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetAllOrdersPage"></a>

## GET 聚合查询所有充提币订单记录

GET /api/v1/private/assets/getAllOrdersPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|startTime|query|string| 否 |起始时间，unix time单位为秒|
|endTime|query|string| 否 |结束时间，unix time单位为秒|
|chainId|query|string| 否 |链id|
|typeList|query|string| 否 |订单类型|
|size|query|string| 否 |每页的数量。必须大于0且小于等于100。|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[PageDataAssetOrder](#schemapagedataassetorder)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[AssetOrder](#schemaassetorder)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

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

Asset订单信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|orderId|string(int64)|false|none||订单id|
|time|string(int64)|false|none||订单创建时间|
|type|string|false|none||订单类型|
|status|integer(int32)|false|none||订单状态|
|amount|string|false|none||订单金额|
|fee|string|false|none||订单手续费|
|txId|string|false|none||链上tx_id|
|chain|string|false|none||链|
|address|string|false|none||地址|
|coin|string|false|none||币种|
|chainId|string|false|none||链id|
|transferSenderAccountId|string|false|none||transfer转出账号id|
|transferReceiverAccountId|string|false|none||transfer转入账号id|

#### 枚举值

|属性|值|
|---|---|
|type|UNKNOWN_ORDER_TYPE|
|type|ORDER_TYPE_NORMAL_DEPOSIT|
|type|ORDER_TYPE_CROSS_DEPOSIT|
|type|ORDER_TYPE_NORMAL_WITHDRAW|
|type|ORDER_TYPE_CROSS_WITHDRAW|
|type|ORDER_TYPE_FAST_WITHDRAW|
|type|ORDER_TYPE_TRANSFER_IN|
|type|ORDER_TYPE_TRANSFER_OUT|
|type|UNRECOGNIZED|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[GetCoinRate](#schemagetcoinrate)|false|none||查询币种对USDC/USDT的汇率-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

查询币种对USDC/USDT的汇率-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|rate|string|false|none||none|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[CrossWithdraw](#schemacrosswithdraw)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

跨链提现单

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||提现单id|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|amount|string|false|none||充值数量|
|ethAddress|string|false|none||充值的eth地址，可能与账户里的eth地址不一样。|
|erc20Address|string|false|none||提现资产在L1上ERC20合约地址|
|lpAccountId|string(int64)|false|none||l2接收用户转账的lp账户id|
|lpAccountL2Key|string(int64)|false|none||收款账户L2 key|
|clientCrossWithdrawId|string|false|none||客户自定义id，用于幂等校验|
|fee|string|false|none||手续费|
|chainId|string|false|none||提现到哪条链|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_withdraw_id) 前32个bit|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间。unix时间的小时数，至少要比下单时间晚24个小时|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|status|string|false|none||普通提现单状态|
|collateralTransactionId|string|false|none||关联的抵押品明细id。当 status=SUCCESS_XXX/FAILED_L2_REJECTED 时存在|
|censorTxId|string(int64)|false|none||审查处理序号。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED 时存在|
|censorTime|string(int64)|false|none||审查处理时间。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED 时存在|
|censorFailCode|string|false|none||审查失败错误码。当 status=FAILED_CENSOR_FAILURE 时存在|
|censorFailReason|string|false|none||审查失败原因。当 status=FAILED_CENSOR_FAILURE 时存在|
|l2TxId|string(int64)|false|none||l2推送交易id。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED 时存在|
|l2HandleTime|string(int64)|false|none||l2处理时间。当 status=SUCCESS_L1_CONFIRMING/SUCCESS_L1_WITHDRAWING/SUCCESS_L1_COMPLETED/FAILED_L2_REJECTED 时存在|
|l2RejectCode|string|false|none||l2拒绝错误码。当 status=FAILED_L2_REJECTED 时存在|
|l2RejectReason|string|false|none||l2拒绝原因。当 status=FAILED_L2_REJECTED 时存在|
|l1ConfirmedTx|[L1Tx](#schemal1tx)|false|none||L1交易信息|
|l1ConfirmedTime|string(int64)|false|none||l1交易确认时间|
|l1CompletedTx|[L1Tx](#schemal1tx)|false|none||L1交易信息|
|l1CompletedEthAddress|string|false|none||l1提现完成eth地址|
|l1CompletedTime|string(int64)|false|none||l1提现完成时间|
|l1RejectedReasonCode|string|false|none||l1拒绝原因代码|
|l1RejectedReasonMsg|string|false|none||l1拒绝原因信息|
|riskSignature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|transferOutId|string(int64)|false|none||转出单id|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|status|CROSS_WITHDRAW_UNKNOWN|
|status|CROSS_WITHDRAW_PENDING_RISK_CHECKING|
|status|CROSS_WITHDRAW_PENDING_CHECKING|
|status|CROSS_WITHDRAW_SUCCESS_SUBMIT_CENSOR|
|status|CROSS_WITHDRAW_PENDING_CENSOR_CHECKING_ACCOUNT|
|status|CROSS_WITHDRAW_PENDING_CENSORING|
|status|CROSS_WITHDRAW_PENDING_L2_APPROVING|
|status|CROSS_WITHDRAW_PENDING_L1_SUBMIT|
|status|CROSS_WITHDRAW_PENDING_L1_CONFIRMING|
|status|CROSS_WITHDRAW_SUCCESS|
|status|CROSS_WITHDRAW_FAILED_RISK_CHECK_FAILURE|
|status|CROSS_WITHDRAW_FAILED_TRANSFER_REJECTED|
|status|CROSS_WITHDRAW_FAILED_CENSOR_CHECKING_ACCOUNT_REJECTED|
|status|CROSS_WITHDRAW_FAILED_CENSORING|
|status|CROSS_WITHDRAW_FAILED_L2_REJECTED|
|status|CROSS_WITHDRAW_FAILED_L1_SUBMIT_REJECTED|
|status|CROSS_WITHDRAW_FAILED_L1_REJECTED|
|status|CROSS_WITHDRAW_FAILED_USER_BALANCE_NOT_ENOUGH|
|status|UNRECOGNIZED|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[GetCrossWithdrawSignInfo](#schemagetcrosswithdrawsigninfo)|false|none||查询跨链提现签名需要的信息-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

查询跨链提现签名需要的信息-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|lpAccountId|string|false|none||l2接收用户转账的lp账户id|
|crossWithdrawL2Key|string|false|none||快速提现账户l2Key|
|crossWithdrawMaxAmount|string|false|none||快速跨链最大额度|
|fee|string|false|none||手续费|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[FastWithdraw](#schemafastwithdraw)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

快速提现单

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||提现单id|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|amount|string|false|none||充值数量|
|ethAddress|string|false|none||充值的eth地址，可能与账户里的eth地址不一样。|
|erc20Address|string|false|none||提现资产在L1上ERC20合约地址|
|lpAccountId|string(int64)|false|none||l2接收用户转账的lp账户id|
|lpAccountL2Key|string(int64)|false|none||收款账户L2 key|
|clientFastWithdrawId|string|false|none||客户自定义id，用于幂等校验|
|fee|string|false|none||手续费|
|chainId|string|false|none||提现到哪条链|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_withdraw_id) 前32个bit|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间。unix时间的小时数，至少要比下单时间晚24个小时|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|factRegistryAddress|string|false|none||none|
|fact|string|false|none||none|
|status|string|false|none||普通提现单状态|
|collateralTransactionId|string|false|none||关联的抵押品明细id。当 status=SUCCESS_XXX/FAILED_L2_REJECTED 时存在|
|censorTxId|string(int64)|false|none||审查处理序号。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED 时存在|
|censorTime|string(int64)|false|none||审查处理时间。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED 时存在|
|censorFailCode|string|false|none||审查失败错误码。当 status=FAILED_CENSOR_FAILURE 时存在|
|censorFailReason|string|false|none||审查失败原因。当 status=FAILED_CENSOR_FAILURE 时存在|
|l2TxId|string(int64)|false|none||l2推送交易id。当 status=SUCCESS_XXX/FAILED_CENSOR_FAILURE/FAILED_L2_REJECTED 时存在|
|l2HandleTime|string(int64)|false|none||l2处理时间。当 status=SUCCESS_L1_CONFIRMING/SUCCESS_L1_WITHDRAWING/SUCCESS_L1_COMPLETED/FAILED_L2_REJECTED 时存在|
|l2RejectCode|string|false|none||l2拒绝错误码。当 status=FAILED_L2_REJECTED 时存在|
|l2RejectReason|string|false|none||l2拒绝原因。当 status=FAILED_L2_REJECTED 时存在|
|l1ConfirmedTx|[L1Tx](#schemal1tx)|false|none||L1交易信息|
|l1ConfirmedTime|string(int64)|false|none||l1交易确认时间|
|l1CompletedTime|string(int64)|false|none||l1提现完成时间|
|l1RejectedReasonCode|string|false|none||l1拒绝原因代码|
|l1RejectedReasonMsg|string|false|none||l1拒绝原因信息|
|riskSignature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|transferOutId|string(int64)|false|none||转出单id|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|status|FAST_WITHDRAW_UNKNOWN|
|status|FAST_WITHDRAW_PENDING_RISK_CHECKING|
|status|FAST_WITHDRAW_PENDING_L1_TRY|
|status|FAST_WITHDRAW_PENDING_CHECKING|
|status|FAST_WITHDRAW_PENDING_SUBMIT|
|status|FAST_WITHDRAW_PENDING_CHECKING_ACCOUNT|
|status|FAST_WITHDRAW_PENDING_CENSORING|
|status|FAST_WITHDRAW_PENDING_L1_CONFIRM|
|status|FAST_WITHDRAW_PENDING_L1_CONFIRMING|
|status|FAST_WITHDRAW_PENDING_CENSORING_CONFIRMING|
|status|FAST_WITHDRAW_PENDING_L2_APPROVING|
|status|FAST_WITHDRAW_SUCCESS|
|status|FAST_WITHDRAW_FAILED_RISK_CHECK_FAILURE|
|status|FAST_WITHDRAW_FAILED_L1_TRY_REJECTED|
|status|FAST_WITHDRAW_FAILED_TRANSFER_REJECTED|
|status|FAST_WITHDRAW_FAILED_CHECKING_ACCOUNT_REJECTED|
|status|FAST_WITHDRAW_FAILED_CENSORING|
|status|FAST_WITHDRAW_FAILED_L1_CONFIRM_REJECTED|
|status|FAST_WITHDRAW_FAILED_L1_REJECTED|
|status|FAST_WITHDRAW_FAILED_L2_REJECTED|
|status|UNRECOGNIZED|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[GetFastWithdrawSignInfo](#schemagetfastwithdrawsigninfo)|false|none||查询快速提现签名需要的信息-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

查询快速提现签名需要的信息-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|lpAccountId|string|false|none||l2接收用户转账的lp账户id|
|fastWithdrawL2Key|string|false|none||快速提现账户l2Key|
|fastWithdrawFactRegisterAddress|string|false|none||L1 Fact合约地址|
|fastWithdrawMaxAmount|string|false|none||快速提现最大额度|
|fee|string|false|none||快速提现手续费|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[NormalWithdraw](#schemanormalwithdraw)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

普通提现单

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||提现单id|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|amount|string|false|none||充值数量|
|ethAddress|string|false|none||充值的eth地址，可能与账户里的eth地址不一样。|
|clientWithdrawId|string|false|none||客户自定义id，用于幂等校验|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_withdraw_id) 前32个bit|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间。unix时间的小时数，至少要比下单时间晚24个小时|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|status|string|false|none||普通提现单状态|
|tradeWithdrawId|string(int64)|false|none||对应的交易服务withdraw单id|
|riskSignature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|l1ConfirmedTx|[L1Tx](#schemal1tx)|false|none||L1交易信息|
|l1ConfirmedTime|string(int64)|false|none||l1交易确认时间|
|l1CompletedTime|string(int64)|false|none||l1提现完成时间|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|status|NORMAL_WITHDRAW_UNKNOWN|
|status|NORMAL_WITHDRAW_PENDING_RISK_CHECKING|
|status|NORMAL_WITHDRAW_PENDING_TRADE_PROCESSING|
|status|NORMAL_WITHDRAW_PENDING_L2_APPROVING|
|status|NORMAL_WITHDRAW_PENDING_L1_CONFIRMING|
|status|NORMAL_WITHDRAW_PENDING_L1_WITHDRAWING|
|status|NORMAL_WITHDRAW_SUCCESS_L1_COMPLETED|
|status|NORMAL_WITHDRAW_FAILED_RISK_CHECK_FAILURE|
|status|NORMAL_WITHDRAW_FAILED_CENSOR_FAILURE|
|status|NORMAL_WITHDRAW_FAILED_L2_REJECTED|
|status|UNRECOGNIZED|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[GetNormalWithdrawableAmount](#schemagetnormalwithdrawableamount)|false|none||根据用户地址查询普通提现claim金额-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

根据用户地址查询普通提现claim金额-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|amount|string|false|none||可提现金额|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[CreateCrossWithdraw](#schemacreatecrosswithdraw)|false|none||创建跨链提现单-相应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

创建跨链提现单-相应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|crossWithdrawId|string(int64)|false|none||跨链提现单Id|

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

创建跨链提现单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||币id|
|amount|string|false|none||提现数量|
|ethAddress|string|false|none||提现到的地址。如果为空，则提到本账号对应的地址。|
|erc20Address|string|false|none||提现资产在L1上ERC20合约地址。|
|lpAccountId|string|false|none||l2接收用户转账的lp账户id|
|clientCrossWithdrawId|string|false|none||客户自定义id，用于签名&幂等校验。必须填写。|
|expireTime|string(int64)|false|none||过期时间|
|l2Signature|string|false|none||提交l2的签名|
|fee|string|false|none||前端获取到的gas+手续费费|
|chainId|string|false|none||提现到哪条链|
|mpcAddress|string|false|none||哪个mpc地址发起的提现|
|mpcSignature|string|false|none||mpc地址对提现字段的签名|
|mpcSignTime|string|false|none||mpc签名时间戳,unix timestamp 单位为秒|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[CreateFastWithdraw](#schemacreatefastwithdraw)|false|none||创建快速提现单-相应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

创建快速提现单-相应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|fastWithdrawId|string(int64)|false|none||快速提现单Id|

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

创建快速提现单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||币id|
|amount|string|false|none||提现数量|
|ethAddress|string|false|none||提现到的地址。如果为空，则提到本账号对应的地址。|
|erc20Address|string|false|none||提现资产在L1上ERC20合约地址。|
|lpAccountId|string|false|none||l2接收用户转账的lp账户id|
|clientFastWithdrawId|string|false|none||客户自定义id，用于签名&幂等校验。必须填写。|
|expireTime|string(int64)|false|none||过期时间|
|l2Signature|string|false|none||提交l2的签名|
|fee|string|false|none||前端获取到的gas+手续费费|
|factRegistryAddress|string|false|none||快速提现对应的fact合约地址|
|fact|string|false|none||快速提现对应的fact值|
|chainId|string|false|none||提现到哪条链|

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[CreateNormalWithdraw](#schemacreatenormalwithdraw)|false|none||创建普通提现单-相应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

创建普通提现单-相应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|withdrawId|string(int64)|false|none||提现单Id|

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

创建普通提现单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||币id|
|amount|string|false|none||提现数量|
|ethAddress|string|false|none||提现到的地址。如果为空，则提到本账号对应的地址。|
|clientWithdrawId|string|false|none||客户自定义id，用于签名&幂等校验。必须填写。|
|expireTime|string(int64)|false|none||过期时间|
|l2Signature|string|false|none||提交l2的签名|

