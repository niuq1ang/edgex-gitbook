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

# 06.WithdrawPrivateApi

<a id="opIdcreateWithdraw"></a>

## POST 创建提现单

POST /api/v1/private/withdraw/createWithdraw

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateWithdrawParam](#schemacreatewithdrawparam)| 否 |none|

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

<a id="opIdgetWithdrawById"></a>

## GET 根据充值单id批量获取提现单

GET /api/v1/private/withdraw/getWithdrawById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|withdrawIdList|query|string| 否 |提现单id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetWithdrawByClientWithdrawId"></a>

## GET 根据充值单id批量获取提现单

GET /api/v1/private/withdraw/getWithdrawByClientWithdrawId

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|clientWithdrawIdList|query|string| 否 |提现单id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetWithdrawAvailableAmount"></a>

## GET 翻页获取提现单

GET /api/v1/private/withdraw/getWithdrawAvailableAmount

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

<a id="opIdgetActiveWithdraw"></a>

## GET 翻页获取提现单

GET /api/v1/private/withdraw/getActiveWithdraw

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的提现单，如果为空则获取所有抵押品coinId的提现单|
|filterStatusList|query|string| 否 |过滤获取指定状态的提现单，不填的话所有状态提现单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的提现单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 |过滤获取指定结束时间创建的提现单 (不包含)，不填或者为0的话就到最近|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

# 数据模型

<h2 id="tocS_Result<PageData<Withdraw>>">Result<PageData<Withdraw>></h2>

<a id="schemaresult<pagedata<withdraw>>"></a>
<a id="schema_Result<PageData<Withdraw>>"></a>
<a id="tocSresult<pagedata<withdraw>>"></a>
<a id="tocsresult<pagedata<withdraw>>"></a>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[PageDataWithdraw](#schemapagedatawithdraw)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataWithdraw">PageDataWithdraw</h2>

<a id="schemapagedatawithdraw"></a>
<a id="schema_PageDataWithdraw"></a>
<a id="tocSpagedatawithdraw"></a>
<a id="tocspagedatawithdraw"></a>

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
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[Withdraw](#schemawithdraw)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Withdraw">Withdraw</h2>

<a id="schemawithdraw"></a>
<a id="schema_Withdraw"></a>
<a id="tocSwithdraw"></a>
<a id="tocswithdraw"></a>

```json
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

```

提现单

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||提现单id|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|amount|string|false|none||提现数量|
|ethAddress|string|false|none||提现到的地址。|
|erc20Address|string|false|none||提现的币种合约地址|
|clientWithdrawId|string|false|none||客户自定义id，用于幂等校验|
|riskSignature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_withdraw_id) 前32个bit|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间，单位毫秒。参与签名生成/校验时要取小时数，即 l2_expire_time / 3600000|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|status|string|false|none||提现单状态|
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
|status|UNKNOWN_WITHDRAW_STATUS|
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

<h2 id="tocS_Result<GetWithdrawAvailableAmount>">Result<GetWithdrawAvailableAmount></h2>

<a id="schemaresult<getwithdrawavailableamount>"></a>
<a id="schema_Result<GetWithdrawAvailableAmount>"></a>
<a id="tocSresult<getwithdrawavailableamount>"></a>
<a id="tocsresult<getwithdrawavailableamount>"></a>

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
|data|[GetWithdrawAvailableAmount](#schemagetwithdrawavailableamount)|false|none||获取提现可用数量-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetWithdrawAvailableAmount">GetWithdrawAvailableAmount</h2>

<a id="schemagetwithdrawavailableamount"></a>
<a id="schema_GetWithdrawAvailableAmount"></a>
<a id="tocSgetwithdrawavailableamount"></a>
<a id="tocsgetwithdrawavailableamount"></a>

```json
{
  "availableAmount": "string"
}

```

获取提现可用数量-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|availableAmount|string(decimal)|false|none||可用数量|

<h2 id="tocS_Result<List<Withdraw>>">Result<List<Withdraw>></h2>

<a id="schemaresult<list<withdraw>>"></a>
<a id="schema_Result<List<Withdraw>>"></a>
<a id="tocSresult<list<withdraw>>"></a>
<a id="tocsresult<list<withdraw>>"></a>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[Withdraw](#schemawithdraw)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Result<CreateWithdraw>">Result<CreateWithdraw></h2>

<a id="schemaresult<createwithdraw>"></a>
<a id="schema_Result<CreateWithdraw>"></a>
<a id="tocSresult<createwithdraw>"></a>
<a id="tocsresult<createwithdraw>"></a>

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
|data|[CreateWithdraw](#schemacreatewithdraw)|false|none||创建提现单-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CreateWithdraw">CreateWithdraw</h2>

<a id="schemacreatewithdraw"></a>
<a id="schema_CreateWithdraw"></a>
<a id="tocScreatewithdraw"></a>
<a id="tocscreatewithdraw"></a>

```json
{
  "withdrawId": "string"
}

```

创建提现单-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|withdrawId|string(int64)|false|none||提现单id|

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

<h2 id="tocS_CreateWithdrawParam">CreateWithdrawParam</h2>

<a id="schemacreatewithdrawparam"></a>
<a id="schema_CreateWithdrawParam"></a>
<a id="tocScreatewithdrawparam"></a>
<a id="tocscreatewithdrawparam"></a>

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

创建提现单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|coinId|string(int64)|false|none||币id|
|amount|string(decimal)|false|none||提现数量|
|ethAddress|string|false|none||提现到的地址。|
|erc20Address|string|false|none||提现的币种合约地址|
|clientWithdrawId|string|false|none||客户自定义id，用于幂等校验|
|riskSignature|string|false|none||风控签名|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_withdraw_id) 前32个bit|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间，单位毫秒。参与签名生成/校验时要取小时数，即 l2_expire_time / 3600000|
|l2Signature|string|false|none||提交l2的签名|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|

