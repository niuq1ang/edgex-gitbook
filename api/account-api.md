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

# 03.AccountPrivateApi

<a id="opIdupdateLeverageSetting"></a>

## POST 更新账户交易杠杆设置

POST /api/v1/private/account/updateLeverageSetting

> Body 请求参数

```json
{
  "accountId": "string",
  "contractId": "string",
  "leverage": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[UpdateLeverageSettingParam](#schemaupdateleveragesettingparam)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {},
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

<a id="opIdupdateFeeSetting"></a>

## POST 更新账户交易手续费设置

POST /api/v1/private/account/updateFeeSetting

> Body 请求参数

```json
{
  "accountId": "string",
  "contractId": "string",
  "isSetFeeRate": true,
  "takerFeeRate": "string",
  "makerFeeRate": "string",
  "isSetFeeDiscount": true,
  "takerFeeDiscount": "string",
  "makerFeeDiscount": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[UpdateFeeSettingParam](#schemaupdatefeesettingparam)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {},
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

<a id="opIdregisterAccount"></a>

## POST 注册账户

POST /api/v1/private/account/registerAccount

> Body 请求参数

```json
{
  "l2Key": "string",
  "l2KeyYCoordinate": "string",
  "clientAccountId": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[RegisterAccountParam](#schemaregisteraccountparam)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {
    "accountId": "string"
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

<a id="opIdgetPositionTransactionPage"></a>

## GET 翻页获取仓位流水

GET /api/v1/private/account/getPositionTransactionPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |获取指定币种的仓位流水，如果不填则获取所有抵押品流水|
|filterContractIdList|query|string| 否 |获取指定合约的仓位流水，如果不填则获取所有仓位流水|
|filterTypeList|query|string| 否 |获取指定持仓变动明细类型的仓位流水，如果不填则获取所有仓位流水|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的仓位流水 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 |过滤获取指定结束时间创建的仓位流水 (不包含)，不填或者为0的话就到最近|
|filterCloseOnly|query|string| 否 |是否仅返回包含平仓的仓位流水。true：只返回有平仓的流水，false：返回所有流水|
|filterOpenOnly|query|string| 否 |是否仅返回包含开仓的仓位流水。true：只返回有开仓的流水，false：返回所有流水|

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

<a id="opIdgetPositionTransactionById"></a>

## GET 根据账户id和仓位流水id批量获取仓位流水

GET /api/v1/private/account/getPositionTransactionById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|positionTransactionIdList|query|string| 否 |仓位流水id|

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

<a id="opIdgetPositionTermPage"></a>

## GET 根据账号id翻页获取持仓term信息

GET /api/v1/private/account/getPositionTermPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |获取指定币种的仓位term信息，如果不填则获取所有仓位term信息|
|filterContractIdList|query|string| 否 |获取指定合约的仓位term信息，如果不填则获取所有仓位term信息|
|filterIsLongPosition|query|string| 否 |获取制定方向的仓位term信息，如果不填则获取所有仓位term信息|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的抵押品流水 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 |过滤获取指定结束时间创建的抵押品流水 (不包含)，不填或者为0的话就到最近|

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

<a id="opIdgetCollateralByCoinId"></a>

## GET 根据账号id和合约id批量获取仓位

GET /api/v1/private/account/getPositionByContractId

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|contractIdList|query|string| 否 |指定的合约id|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "openSize": "string",
      "openValue": "string",
      "openFee": "string",
      "fundingFee": "string",
      "longTermCount": 0,
      "longTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "longTermCreatedTime": "string",
      "longTermUpdatedTime": "string",
      "shortTermCount": 0,
      "shortTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTermCreatedTime": "string",
      "shortTermUpdatedTime": "string",
      "longTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
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

<a id="opIdgetCollateralTransactionPage"></a>

## GET 根据账户id翻页获取抵押品明细

GET /api/v1/private/account/getCollateralTransactionPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |获取指定币种的抵押品流水，如果不填则获取所有抵押品流水|
|filterTypeList|query|string| 否 |获取指定抵押品变动明细类型的流水，如果不填则获取所有抵押品流水|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的抵押品流水 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 |过滤获取指定结束时间创建的抵押品流水 (不包含)，不填或者为0的话就到最近|

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
        "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
        "deltaAmount": "string",
        "deltaLegacyAmount": "string",
        "beforeAmount": "string",
        "beforeLegacyAmount": "string",
        "fillCloseSize": "string",
        "fillCloseValue": "string",
        "fillCloseFee": "string",
        "fillOpenSize": "string",
        "fillOpenValue": "string",
        "fillOpenFee": "string",
        "fillPrice": "string",
        "liquidateFee": "string",
        "realizePnl": "string",
        "isLiquidate": true,
        "isDeleverage": true,
        "fundingTime": "string",
        "fundingRate": "string",
        "fundingIndexPrice": "string",
        "fundingOraclePrice": "string",
        "fundingPositionSize": "string",
        "depositId": "string",
        "withdrawId": "string",
        "transferInId": "string",
        "transferOutId": "string",
        "transferReason": "UNKNOWN_TRANSFER_REASON",
        "orderId": "string",
        "orderFillTransactionId": "string",
        "orderAccountId": "string",
        "positionContractId": "string",
        "positionTransactionId": "string",
        "forceWithdrawId": "string",
        "forceTradeId": "string",
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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetCollateralTransactionById"></a>

## GET 根据账户id和抵押品明细id批量获取成抵押品明细

GET /api/v1/private/account/getCollateralTransactionById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|collateralTransactionIdList|query|string| 否 |抵押品明细id|

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
      "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
      "deltaAmount": "string",
      "deltaLegacyAmount": "string",
      "beforeAmount": "string",
      "beforeLegacyAmount": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "depositId": "string",
      "withdrawId": "string",
      "transferInId": "string",
      "transferOutId": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "orderAccountId": "string",
      "positionContractId": "string",
      "positionTransactionId": "string",
      "forceWithdrawId": "string",
      "forceTradeId": "string",
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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetCollateralByCoinId_1"></a>

## GET 根据账号id和抵押品coinId批量获取抵押品信息

GET /api/v1/private/account/getCollateralByCoinId

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|coinIdList|query|string| 否 |获取指定币种的抵押品信息，如果不填则获取所有抵押品信息|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "amount": "string",
      "legacyAmount": "string",
      "cumDepositAmount": "string",
      "cumWithdrawAmount": "string",
      "cumTransferInAmount": "string",
      "cumTransferOutAmount": "string",
      "cumPositionBuyAmount": "string",
      "cumPositionSellAmount": "string",
      "cumFillFeeAmount": "string",
      "cumFundingFeeAmount": "string",
      "cumFillFeeIncomeAmount": "string",
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

<a id="opIdgetAccountPage"></a>

## GET 根据用户id翻页获取账户信息

GET /api/v1/private/account/getAccountPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
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

<a id="opIdgetAccountDeleverageLight"></a>

## GET 获取账户下所有仓位减仓ADL灯

GET /api/v1/private/account/getAccountDeleverageLight

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|

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

<a id="opIdgetAccountById"></a>

## GET 根据账户id获取账户信息

GET /api/v1/private/account/getAccountById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|

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

<a id="opIdgetAccountAsset"></a>

## GET 获取账户资产相关数据

GET /api/v1/private/account/getAccountAsset

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|

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

<a id="opIdgetAccountAssetSnapshotPage"></a>

## GET 根据账号id翻页获取历史资产快照

GET /api/v1/private/account/getAccountAssetSnapshotPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于1000|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|coinId|query|string| 是 |获取指定币种的资产快照|
|filterTimeTag|query|string| 否 |指定时间tag 不填或者为0的话按小时返回快照，1按天返回快照|
|filterStartTimeInclusive|query|string| 否 |过滤获取指定开始时间的资产快照 (包含)，不填或者为0的话就从最早开始|
|filterEndTimeExclusive|query|string| 否 |过滤获取指定结束时间的资产快照 (不包含)，不填或者为0的话就到最近|

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

<h2 id="tocS_Result<PageData<AccountAssetSnapshot>>">Result<PageData<AccountAssetSnapshot>></h2>

<a id="schemaresult<pagedata<accountassetsnapshot>>"></a>
<a id="schema_Result<PageData<AccountAssetSnapshot>>"></a>
<a id="tocSresult<pagedata<accountassetsnapshot>>"></a>
<a id="tocsresult<pagedata<accountassetsnapshot>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "timeTag": 0,
        "snapshotTime": "string",
        "totalEquity": "string",
        "termRealizePnl": "string",
        "unrealizePnl": "string",
        "totalRealizePnl": "string"
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
|data|[PageDataAccountAssetSnapshot](#schemapagedataaccountassetsnapshot)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataAccountAssetSnapshot">PageDataAccountAssetSnapshot</h2>

<a id="schemapagedataaccountassetsnapshot"></a>
<a id="schema_PageDataAccountAssetSnapshot"></a>
<a id="tocSpagedataaccountassetsnapshot"></a>
<a id="tocspagedataaccountassetsnapshot"></a>

```json
{
  "dataList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "timeTag": 0,
      "snapshotTime": "string",
      "totalEquity": "string",
      "termRealizePnl": "string",
      "unrealizePnl": "string",
      "totalRealizePnl": "string"
    }
  ],
  "nextPageOffsetData": "string"
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[AccountAssetSnapshot](#schemaaccountassetsnapshot)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_AccountAssetSnapshot">AccountAssetSnapshot</h2>

<a id="schemaaccountassetsnapshot"></a>
<a id="schema_AccountAssetSnapshot"></a>
<a id="tocSaccountassetsnapshot"></a>
<a id="tocsaccountassetsnapshot"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "timeTag": 0,
  "snapshotTime": "string",
  "totalEquity": "string",
  "termRealizePnl": "string",
  "unrealizePnl": "string",
  "totalRealizePnl": "string"
}

```

账户历史资产快照信息数据

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|timeTag|integer(int32)|false|none||时间标记 1表示当前的快照时间为整天|
|snapshotTime|string(int64)|false|none||快照时间。这个数据每小时统计一次。小时整点时间戳|
|totalEquity|string|false|none||当前抵押品总价值|
|termRealizePnl|string|false|none||term已实现盈亏|
|unrealizePnl|string|false|none||未实现盈亏|
|totalRealizePnl|string|false|none||仓位total已实现盈亏|

<h2 id="tocS_Result<GetAccountAsset>">Result<GetAccountAsset></h2>

<a id="schemaresult<getaccountasset>"></a>
<a id="schema_Result<GetAccountAsset>"></a>
<a id="tocSresult<getaccountasset>"></a>
<a id="tocsresult<getaccountasset>"></a>

```json
{
  "code": "string",
  "data": {
    "account": {
      "id": "string",
      "userId": "string",
      "ethAddress": "string",
      "l2Key": "string",
      "l2KeyYCoordinate": "string",
      "clientAccountId": "string",
      "isSystemAccount": true,
      "defaultTradeSetting": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      },
      "contractIdToTradeSetting": {
        "property1": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        },
        "property2": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        }
      },
      "maxLeverageLimit": "string",
      "createOrderPerMinuteLimit": 0,
      "createOrderDelayMillis": 0,
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ACCOUNT_STATUS",
      "isLiquidating": true,
      "createdTime": "string",
      "updatedTime": "string"
    },
    "collateralList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "amount": "string",
        "legacyAmount": "string",
        "cumDepositAmount": "string",
        "cumWithdrawAmount": "string",
        "cumTransferInAmount": "string",
        "cumTransferOutAmount": "string",
        "cumPositionBuyAmount": "string",
        "cumPositionSellAmount": "string",
        "cumFillFeeAmount": "string",
        "cumFundingFeeAmount": "string",
        "cumFillFeeIncomeAmount": "string",
        "createdTime": "string",
        "updatedTime": "string"
      }
    ],
    "positionList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "openSize": "string",
        "openValue": "string",
        "openFee": "string",
        "fundingFee": "string",
        "longTermCount": 0,
        "longTermStat": {
          "cumOpenSize": "string",
          "cumOpenValue": "string",
          "cumOpenFee": "string",
          "cumCloseSize": "string",
          "cumCloseValue": "string",
          "cumCloseFee": "string",
          "cumFundingFee": "string",
          "cumLiquidateFee": "string"
        },
        "longTermCreatedTime": "string",
        "longTermUpdatedTime": "string",
        "shortTermCount": 0,
        "shortTermStat": {
          "cumOpenSize": "string",
          "cumOpenValue": "string",
          "cumOpenFee": "string",
          "cumCloseSize": "string",
          "cumCloseValue": "string",
          "cumCloseFee": "string",
          "cumFundingFee": "string",
          "cumLiquidateFee": "string"
        },
        "shortTermCreatedTime": "string",
        "shortTermUpdatedTime": "string",
        "longTotalStat": {
          "cumOpenSize": "string",
          "cumOpenValue": "string",
          "cumOpenFee": "string",
          "cumCloseSize": "string",
          "cumCloseValue": "string",
          "cumCloseFee": "string",
          "cumFundingFee": "string",
          "cumLiquidateFee": "string"
        },
        "shortTotalStat": {
          "cumOpenSize": "string",
          "cumOpenValue": "string",
          "cumOpenFee": "string",
          "cumCloseSize": "string",
          "cumCloseValue": "string",
          "cumCloseFee": "string",
          "cumFundingFee": "string",
          "cumLiquidateFee": "string"
        },
        "createdTime": "string",
        "updatedTime": "string"
      }
    ],
    "version": "string",
    "positionAssetList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "positionValue": "string",
        "maxLeverage": "string",
        "initialMarginRequirement": "string",
        "starkExRiskRate": "string",
        "starkExRiskValue": "string",
        "avgEntryPrice": "string",
        "liquidatePrice": "string",
        "bankruptPrice": "string",
        "worstClosePrice": "string",
        "unrealizePnl": "string",
        "termRealizePnl": "string",
        "totalRealizePnl": "string"
      }
    ],
    "collateralAssetModelList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "totalEquity": "string",
        "totalPositionValueAbs": "string",
        "initialMarginRequirement": "string",
        "starkExRiskValue": "string",
        "pendingWithdrawAmount": "string",
        "pendingTransferOutAmount": "string",
        "orderFrozenAmount": "string",
        "availableAmount": "string"
      }
    ],
    "oraclePriceList": [
      {
        "contractId": "string",
        "priceType": "UNKNOWN_PRICE_TYPE",
        "priceValue": "string",
        "createdTime": "string",
        "oraclePriceSignature": [
          {
            "contractId": null,
            "signer": null,
            "price": null,
            "externalAssetId": null,
            "signature": null,
            "timestamp": null
          }
        ]
      }
    ]
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
|data|[GetAccountAsset](#schemagetaccountasset)|false|none||获取账户资产相关数据-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetAccountAsset">GetAccountAsset</h2>

<a id="schemagetaccountasset"></a>
<a id="schema_GetAccountAsset"></a>
<a id="tocSgetaccountasset"></a>
<a id="tocsgetaccountasset"></a>

```json
{
  "account": {
    "id": "string",
    "userId": "string",
    "ethAddress": "string",
    "l2Key": "string",
    "l2KeyYCoordinate": "string",
    "clientAccountId": "string",
    "isSystemAccount": true,
    "defaultTradeSetting": {
      "isSetFeeRate": true,
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "isSetFeeDiscount": true,
      "takerFeeDiscount": "string",
      "makerFeeDiscount": "string",
      "isSetMaxLeverage": true,
      "maxLeverage": "string"
    },
    "contractIdToTradeSetting": {
      "property1": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      },
      "property2": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      }
    },
    "maxLeverageLimit": "string",
    "createOrderPerMinuteLimit": 0,
    "createOrderDelayMillis": 0,
    "extraType": "string",
    "extraDataJson": "string",
    "status": "UNKNOWN_ACCOUNT_STATUS",
    "isLiquidating": true,
    "createdTime": "string",
    "updatedTime": "string"
  },
  "collateralList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "amount": "string",
      "legacyAmount": "string",
      "cumDepositAmount": "string",
      "cumWithdrawAmount": "string",
      "cumTransferInAmount": "string",
      "cumTransferOutAmount": "string",
      "cumPositionBuyAmount": "string",
      "cumPositionSellAmount": "string",
      "cumFillFeeAmount": "string",
      "cumFundingFeeAmount": "string",
      "cumFillFeeIncomeAmount": "string",
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "positionList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "openSize": "string",
      "openValue": "string",
      "openFee": "string",
      "fundingFee": "string",
      "longTermCount": 0,
      "longTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "longTermCreatedTime": "string",
      "longTermUpdatedTime": "string",
      "shortTermCount": 0,
      "shortTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTermCreatedTime": "string",
      "shortTermUpdatedTime": "string",
      "longTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "createdTime": "string",
      "updatedTime": "string"
    }
  ],
  "version": "string",
  "positionAssetList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "positionValue": "string",
      "maxLeverage": "string",
      "initialMarginRequirement": "string",
      "starkExRiskRate": "string",
      "starkExRiskValue": "string",
      "avgEntryPrice": "string",
      "liquidatePrice": "string",
      "bankruptPrice": "string",
      "worstClosePrice": "string",
      "unrealizePnl": "string",
      "termRealizePnl": "string",
      "totalRealizePnl": "string"
    }
  ],
  "collateralAssetModelList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "totalEquity": "string",
      "totalPositionValueAbs": "string",
      "initialMarginRequirement": "string",
      "starkExRiskValue": "string",
      "pendingWithdrawAmount": "string",
      "pendingTransferOutAmount": "string",
      "orderFrozenAmount": "string",
      "availableAmount": "string"
    }
  ],
  "oraclePriceList": [
    {
      "contractId": "string",
      "priceType": "UNKNOWN_PRICE_TYPE",
      "priceValue": "string",
      "createdTime": "string",
      "oraclePriceSignature": [
        {
          "contractId": "string",
          "signer": "string",
          "price": "string",
          "externalAssetId": "string",
          "signature": {
            "r": null,
            "s": null,
            "v": null
          },
          "timestamp": "string"
        }
      ]
    }
  ]
}

```

获取账户资产相关数据-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|account|[Account](#schemaaccount)|false|none||账户信息数据|
|collateralList|[[Collateral](#schemacollateral)]|false|none||抵押品信息列表|
|positionList|[[Position](#schemaposition)]|false|none||永续合约仓位信息列表|
|version|string(int64)|false|none||账户版本号，每更新一次都会 +1|
|positionAssetList|[[PositionAsset](#schemapositionasset)]|false|none||仓位的资产信息|
|collateralAssetModelList|[[CollateralAsset](#schemacollateralasset)]|false|none||账户级别资产信息|
|oraclePriceList|[[IndexPrice](#schemaindexprice)]|false|none||计算资产时所使用的所有预言机价格(仅使用到的，不是所有的)|

<h2 id="tocS_IndexPrice">IndexPrice</h2>

<a id="schemaindexprice"></a>
<a id="schema_IndexPrice"></a>
<a id="tocSindexprice"></a>
<a id="tocsindexprice"></a>

```json
{
  "contractId": "string",
  "priceType": "UNKNOWN_PRICE_TYPE",
  "priceValue": "string",
  "createdTime": "string",
  "oraclePriceSignature": [
    {
      "contractId": "string",
      "signer": "string",
      "price": "string",
      "externalAssetId": "string",
      "signature": {
        "r": "string",
        "s": "string",
        "v": "string"
      },
      "timestamp": "string"
    }
  ]
}

```

价格信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约id|
|priceType|string|false|none||价格类型|
|priceValue|string|false|none||价格取值|
|createdTime|string(int64)|false|none||创建时间|
|oraclePriceSignature|[[OraclePriceSignature](#schemaoraclepricesignature)]|false|none||预言机价格签名信息，仅当 price_type=ORACLE_PRICE 时存在|

#### 枚举值

|属性|值|
|---|---|
|priceType|UNKNOWN_PRICE_TYPE|
|priceType|ORACLE_PRICE|
|priceType|INDEX_PRICE|
|priceType|LAST_PRICE|
|priceType|ASK1_PRICE|
|priceType|BID1_PRICE|
|priceType|OPEN_INTEREST|
|priceType|UNRECOGNIZED|

<h2 id="tocS_OraclePriceSignature">OraclePriceSignature</h2>

<a id="schemaoraclepricesignature"></a>
<a id="schema_OraclePriceSignature"></a>
<a id="tocSoraclepricesignature"></a>
<a id="tocsoraclepricesignature"></a>

```json
{
  "contractId": "string",
  "signer": "string",
  "price": "string",
  "externalAssetId": "string",
  "signature": {
    "r": "string",
    "s": "string",
    "v": "string"
  },
  "timestamp": "string"
}

```

预言机价格签名信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约id|
|signer|string|false|none||签名者标识|
|price|string|false|none||签名价格 (按照stark ex 精度处理后的价格)|
|externalAssetId|string|false|none||Concatenation of the asset name and the oracle name (both in hex encoding).|
|signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|timestamp|string(int64)|false|none||The time the signature was created.|

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

<h2 id="tocS_CollateralAsset">CollateralAsset</h2>

<a id="schemacollateralasset"></a>
<a id="schema_CollateralAsset"></a>
<a id="tocScollateralasset"></a>
<a id="tocscollateralasset"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "totalEquity": "string",
  "totalPositionValueAbs": "string",
  "initialMarginRequirement": "string",
  "starkExRiskValue": "string",
  "pendingWithdrawAmount": "string",
  "pendingTransferOutAmount": "string",
  "orderFrozenAmount": "string",
  "availableAmount": "string"
}

```

抵押品资产信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|totalEquity|string|false|none||当前抵押品下的总价值|
|totalPositionValueAbs|string|false|none||当前抵押品对应的仓位价值绝对值之和|
|initialMarginRequirement|string|false|none||当前抵押品下的初始保证金|
|starkExRiskValue|string|false|none||当前抵押品下的总 starkEx 风险金额|
|pendingWithdrawAmount|string|false|none||当前抵押品处理中的提现金额|
|pendingTransferOutAmount|string|false|none||当前抵押品处理中的转出金额|
|orderFrozenAmount|string|false|none||当前抵押品所属委托单冻结金额|
|availableAmount|string|false|none||当前抵押品可用金额|

<h2 id="tocS_PositionAsset">PositionAsset</h2>

<a id="schemapositionasset"></a>
<a id="schema_PositionAsset"></a>
<a id="tocSpositionasset"></a>
<a id="tocspositionasset"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "positionValue": "string",
  "maxLeverage": "string",
  "initialMarginRequirement": "string",
  "starkExRiskRate": "string",
  "starkExRiskValue": "string",
  "avgEntryPrice": "string",
  "liquidatePrice": "string",
  "bankruptPrice": "string",
  "worstClosePrice": "string",
  "unrealizePnl": "string",
  "termRealizePnl": "string",
  "totalRealizePnl": "string"
}

```

仓位相关的资产信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|contractId|string(int64)|false|none||所属合约id|
|positionValue|string|false|none||仓位价值，(正数为多仓，负数为空仓)|
|maxLeverage|string|false|none||当前合约仓位最大可开杠杆|
|initialMarginRequirement|string|false|none||仓位初始保证金|
|starkExRiskRate|string|false|none||结合风险档位计算出的starkEx风险率。本质类似于维持保证金率，只是精度不同|
|starkExRiskValue|string|false|none||starkEx 风险金额，本质类似于维持保证金，只是精度不同。|
|avgEntryPrice|string|false|none||平均入场价格|
|liquidatePrice|string|false|none||清算价(强平价)。即当预言机价格到达此价格，必定触发清算|
|bankruptPrice|string|false|none||破产价。即当预言机价格到达此价格，账户总价值小于0|
|worstClosePrice|string|false|none||最差平仓价。即平仓成交价格不能劣于这个价格|
|unrealizePnl|string|false|none||仓位未实现盈亏|
|termRealizePnl|string|false|none||仓位term已实现盈亏|
|totalRealizePnl|string|false|none||仓位total已实现盈亏|

<h2 id="tocS_Position">Position</h2>

<a id="schemaposition"></a>
<a id="schema_Position"></a>
<a id="tocSposition"></a>
<a id="tocsposition"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "openSize": "string",
  "openValue": "string",
  "openFee": "string",
  "fundingFee": "string",
  "longTermCount": 0,
  "longTermStat": {
    "cumOpenSize": "string",
    "cumOpenValue": "string",
    "cumOpenFee": "string",
    "cumCloseSize": "string",
    "cumCloseValue": "string",
    "cumCloseFee": "string",
    "cumFundingFee": "string",
    "cumLiquidateFee": "string"
  },
  "longTermCreatedTime": "string",
  "longTermUpdatedTime": "string",
  "shortTermCount": 0,
  "shortTermStat": {
    "cumOpenSize": "string",
    "cumOpenValue": "string",
    "cumOpenFee": "string",
    "cumCloseSize": "string",
    "cumCloseValue": "string",
    "cumCloseFee": "string",
    "cumFundingFee": "string",
    "cumLiquidateFee": "string"
  },
  "shortTermCreatedTime": "string",
  "shortTermUpdatedTime": "string",
  "longTotalStat": {
    "cumOpenSize": "string",
    "cumOpenValue": "string",
    "cumOpenFee": "string",
    "cumCloseSize": "string",
    "cumCloseValue": "string",
    "cumCloseFee": "string",
    "cumFundingFee": "string",
    "cumLiquidateFee": "string"
  },
  "shortTotalStat": {
    "cumOpenSize": "string",
    "cumOpenValue": "string",
    "cumOpenFee": "string",
    "cumCloseSize": "string",
    "cumCloseValue": "string",
    "cumCloseFee": "string",
    "cumFundingFee": "string",
    "cumLiquidateFee": "string"
  },
  "createdTime": "string",
  "updatedTime": "string"
}

```

永续合约持仓信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|contractId|string(int64)|false|none||所属合约id|
|openSize|string|false|none||当前开仓数量 (正数为多仓，负数为空仓)|
|openValue|string|false|none||当前开仓价值 (开仓会累加，平仓会等比例减少)|
|openFee|string|false|none||当前开仓均摊后的手续费 (开仓会累加，平仓会等比例减少)|
|fundingFee|string|false|none||当前仓位均摊后的资金费用 (结算时会累加，平仓会等比例减少)|
|longTermCount|integer(int32)|false|none||多仓term次数。从1开始，每次完全平仓后会加一。|
|longTermStat|[PositionStat](#schemapositionstat)|false|none||仓位累计统计信息|
|longTermCreatedTime|string|false|none||多仓term创建时间|
|longTermUpdatedTime|string|false|none||多仓term创建时间|
|shortTermCount|integer(int32)|false|none||空仓term次数。从1开始，每次完全平仓后会加一。|
|shortTermStat|[PositionStat](#schemapositionstat)|false|none||仓位累计统计信息|
|shortTermCreatedTime|string|false|none||空仓term创建时间|
|shortTermUpdatedTime|string|false|none||空仓term创建时间|
|longTotalStat|[PositionStat](#schemapositionstat)|false|none||仓位累计统计信息|
|shortTotalStat|[PositionStat](#schemapositionstat)|false|none||仓位累计统计信息|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

<h2 id="tocS_PositionStat">PositionStat</h2>

<a id="schemapositionstat"></a>
<a id="schema_PositionStat"></a>
<a id="tocSpositionstat"></a>
<a id="tocspositionstat"></a>

```json
{
  "cumOpenSize": "string",
  "cumOpenValue": "string",
  "cumOpenFee": "string",
  "cumCloseSize": "string",
  "cumCloseValue": "string",
  "cumCloseFee": "string",
  "cumFundingFee": "string",
  "cumLiquidateFee": "string"
}

```

仓位累计统计信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|cumOpenSize|string|false|none||累计开仓数量|
|cumOpenValue|string|false|none||累计开仓价值|
|cumOpenFee|string|false|none||累计开仓费用|
|cumCloseSize|string|false|none||累计平仓数量|
|cumCloseValue|string|false|none||累计平仓价值|
|cumCloseFee|string|false|none||累计平仓费用|
|cumFundingFee|string|false|none||累计已结算的资金费用|
|cumLiquidateFee|string|false|none||累计清算费用|

<h2 id="tocS_Collateral">Collateral</h2>

<a id="schemacollateral"></a>
<a id="schema_Collateral"></a>
<a id="tocScollateral"></a>
<a id="tocscollateral"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "amount": "string",
  "legacyAmount": "string",
  "cumDepositAmount": "string",
  "cumWithdrawAmount": "string",
  "cumTransferInAmount": "string",
  "cumTransferOutAmount": "string",
  "cumPositionBuyAmount": "string",
  "cumPositionSellAmount": "string",
  "cumFillFeeAmount": "string",
  "cumFundingFeeAmount": "string",
  "cumFillFeeIncomeAmount": "string",
  "createdTime": "string",
  "updatedTime": "string"
}

```

抵押品信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||货币id|
|amount|string(decimal)|false|none||抵押品数额, 实际为decimal类型|
|legacyAmount|string(decimal)|false|none||老式记账方式余额字段，仅展示不参与计算|
|cumDepositAmount|string(decimal)|false|none||累计的充值数量|
|cumWithdrawAmount|string(decimal)|false|none||累计的提现数量|
|cumTransferInAmount|string(decimal)|false|none||累计的转入数量|
|cumTransferOutAmount|string(decimal)|false|none||累计的转出数量|
|cumPositionBuyAmount|string(decimal)|false|none||累计仓位买入扣减的抵押品数量|
|cumPositionSellAmount|string(decimal)|false|none||累计仓位卖出增加的抵押品数量|
|cumFillFeeAmount|string(decimal)|false|none||累计的成交手续费数量|
|cumFundingFeeAmount|string(decimal)|false|none||累计资金费用数量|
|cumFillFeeIncomeAmount|string(decimal)|false|none||累计的委托单手续费收入数量|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

<h2 id="tocS_Account">Account</h2>

<a id="schemaaccount"></a>
<a id="schema_Account"></a>
<a id="tocSaccount"></a>
<a id="tocsaccount"></a>

```json
{
  "id": "string",
  "userId": "string",
  "ethAddress": "string",
  "l2Key": "string",
  "l2KeyYCoordinate": "string",
  "clientAccountId": "string",
  "isSystemAccount": true,
  "defaultTradeSetting": {
    "isSetFeeRate": true,
    "takerFeeRate": "string",
    "makerFeeRate": "string",
    "isSetFeeDiscount": true,
    "takerFeeDiscount": "string",
    "makerFeeDiscount": "string",
    "isSetMaxLeverage": true,
    "maxLeverage": "string"
  },
  "contractIdToTradeSetting": {
    "property1": {
      "isSetFeeRate": true,
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "isSetFeeDiscount": true,
      "takerFeeDiscount": "string",
      "makerFeeDiscount": "string",
      "isSetMaxLeverage": true,
      "maxLeverage": "string"
    },
    "property2": {
      "isSetFeeRate": true,
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "isSetFeeDiscount": true,
      "takerFeeDiscount": "string",
      "makerFeeDiscount": "string",
      "isSetMaxLeverage": true,
      "maxLeverage": "string"
    }
  },
  "maxLeverageLimit": "string",
  "createOrderPerMinuteLimit": 0,
  "createOrderDelayMillis": 0,
  "extraType": "string",
  "extraDataJson": "string",
  "status": "UNKNOWN_ACCOUNT_STATUS",
  "isLiquidating": true,
  "createdTime": "string",
  "updatedTime": "string"
}

```

账户信息数据

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||账户id。取值大于0|
|userId|string(int64)|false|none||所属用户id|
|ethAddress|string|false|none||钱包eth地址|
|l2Key|string|false|none||L2上的账户key。对应starkEx中的starkKey。bigint for hex str|
|l2KeyYCoordinate|string|false|none||只用于验证 l2Signature 是否ok。不返回给C端用户。bigint for hex str|
|clientAccountId|string|false|none||客户端账户id, 用于幂等性校验|
|isSystemAccount|boolean|false|none||是否为系统账号 (系统账户不受合约相关风险设置限制,使用单独的mq发送trade消息)|
|defaultTradeSetting|[TradeSetting](#schematradesetting)|false|none||交易设置. 交易设置计算优先级：账户合约交易设置 -> 账户默认交易设置 -> 合约配置交易设置. 注意：is_set_fee_rate 和 is_set_fee_discount 只能有一个为 true|
|contractIdToTradeSetting|object|false|none||账户合约级别交易设置|
|» **additionalProperties**|[TradeSetting](#schematradesetting)|false|none||交易设置. 交易设置计算优先级：账户合约交易设置 -> 账户默认交易设置 -> 合约配置交易设置. 注意：is_set_fee_rate 和 is_set_fee_discount 只能有一个为 true|
|maxLeverageLimit|string|false|none||用户可设置的最大开仓杠杆限制，如果为0则使用对应交易合约的杠杆限制|
|createOrderPerMinuteLimit|integer(int32)|false|none||下单频率每分钟限制，如果为0使用默认频率限制，如果<0则不限制下单频率|
|createOrderDelayMillis|integer(int32)|false|none||下单延迟毫秒，必须大于等于0|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||附加数据，json格式，默认为空串|
|status|string|false|none||账户状态|
|isLiquidating|boolean|false|none||是否清算中|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|status|UNKNOWN_ACCOUNT_STATUS|
|status|CENSORING|
|status|NORMAL|
|status|DISABLED|
|status|INVALID|
|status|UNRECOGNIZED|

<h2 id="tocS_TradeSetting">TradeSetting</h2>

<a id="schematradesetting"></a>
<a id="schema_TradeSetting"></a>
<a id="tocStradesetting"></a>
<a id="tocstradesetting"></a>

```json
{
  "isSetFeeRate": true,
  "takerFeeRate": "string",
  "makerFeeRate": "string",
  "isSetFeeDiscount": true,
  "takerFeeDiscount": "string",
  "makerFeeDiscount": "string",
  "isSetMaxLeverage": true,
  "maxLeverage": "string"
}

```

交易设置. 交易设置计算优先级：账户合约交易设置 -> 账户默认交易设置 -> 合约配置交易设置. 注意：is_set_fee_rate 和 is_set_fee_discount 只能有一个为 true

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|isSetFeeRate|boolean|false|none||是否设置费率(具体值)|
|takerFeeRate|string(decimal)|false|none||taker费率，取值范围 [0, 1)，仅当 is_set_fee_rate=true 时有效|
|makerFeeRate|string(decimal)|false|none||maker费率，取值范围 [0, 1)，仅当 is_set_fee_rate=true 时有效|
|isSetFeeDiscount|boolean|false|none||是否设置费率折扣|
|takerFeeDiscount|string(decimal)|false|none||taker费率折扣，取值范围 [0, 1)，仅当 is_set_fee_discount=true 时有效|
|makerFeeDiscount|string(decimal)|false|none||maker费率折扣，取值范围 [0, 1)，仅当 is_set_fee_discount=true 时有效|
|isSetMaxLeverage|boolean|false|none||是否设置最大交易杠杆|
|maxLeverage|string(decimal)|false|none||最大交易杠杆|

<h2 id="tocS_Result<Account>">Result<Account></h2>

<a id="schemaresult<account>"></a>
<a id="schema_Result<Account>"></a>
<a id="tocSresult<account>"></a>
<a id="tocsresult<account>"></a>

```json
{
  "code": "string",
  "data": {
    "id": "string",
    "userId": "string",
    "ethAddress": "string",
    "l2Key": "string",
    "l2KeyYCoordinate": "string",
    "clientAccountId": "string",
    "isSystemAccount": true,
    "defaultTradeSetting": {
      "isSetFeeRate": true,
      "takerFeeRate": "string",
      "makerFeeRate": "string",
      "isSetFeeDiscount": true,
      "takerFeeDiscount": "string",
      "makerFeeDiscount": "string",
      "isSetMaxLeverage": true,
      "maxLeverage": "string"
    },
    "contractIdToTradeSetting": {
      "property1": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      },
      "property2": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      }
    },
    "maxLeverageLimit": "string",
    "createOrderPerMinuteLimit": 0,
    "createOrderDelayMillis": 0,
    "extraType": "string",
    "extraDataJson": "string",
    "status": "UNKNOWN_ACCOUNT_STATUS",
    "isLiquidating": true,
    "createdTime": "string",
    "updatedTime": "string"
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
|data|[Account](#schemaaccount)|false|none||账户信息数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Result<GetAccountDeleverageLight>">Result<GetAccountDeleverageLight></h2>

<a id="schemaresult<getaccountdeleveragelight>"></a>
<a id="schema_Result<GetAccountDeleverageLight>"></a>
<a id="tocSresult<getaccountdeleveragelight>"></a>
<a id="tocsresult<getaccountdeleveragelight>"></a>

```json
{
  "code": "string",
  "data": {
    "positionContractIdToLightNumberMap": {
      "property1": 0,
      "property2": 0
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
|data|[GetAccountDeleverageLight](#schemagetaccountdeleveragelight)|false|none||获取账户下所有仓位减仓ADL灯-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetAccountDeleverageLight">GetAccountDeleverageLight</h2>

<a id="schemagetaccountdeleveragelight"></a>
<a id="schema_GetAccountDeleverageLight"></a>
<a id="tocSgetaccountdeleveragelight"></a>
<a id="tocsgetaccountdeleveragelight"></a>

```json
{
  "positionContractIdToLightNumberMap": {
    "property1": 0,
    "property2": 0
  }
}

```

获取账户下所有仓位减仓ADL灯-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|positionContractIdToLightNumberMap|object|false|none||仓位合约id到灯的映射。light_number 取值 1-5，代表1-5盏灯|
|» **additionalProperties**|integer(int32)|false|none||仓位合约id到灯的映射。light_number 取值 1-5，代表1-5盏灯|

<h2 id="tocS_Result<PageData<Account>>">Result<PageData<Account>></h2>

<a id="schemaresult<pagedata<account>>"></a>
<a id="schema_Result<PageData<Account>>"></a>
<a id="tocSresult<pagedata<account>>"></a>
<a id="tocsresult<pagedata<account>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "ethAddress": "string",
        "l2Key": "string",
        "l2KeyYCoordinate": "string",
        "clientAccountId": "string",
        "isSystemAccount": true,
        "defaultTradeSetting": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        },
        "contractIdToTradeSetting": {
          "property1": {
            "isSetFeeRate": null,
            "takerFeeRate": null,
            "makerFeeRate": null,
            "isSetFeeDiscount": null,
            "takerFeeDiscount": null,
            "makerFeeDiscount": null,
            "isSetMaxLeverage": null,
            "maxLeverage": null
          },
          "property2": {
            "isSetFeeRate": null,
            "takerFeeRate": null,
            "makerFeeRate": null,
            "isSetFeeDiscount": null,
            "takerFeeDiscount": null,
            "makerFeeDiscount": null,
            "isSetMaxLeverage": null,
            "maxLeverage": null
          }
        },
        "maxLeverageLimit": "string",
        "createOrderPerMinuteLimit": 0,
        "createOrderDelayMillis": 0,
        "extraType": "string",
        "extraDataJson": "string",
        "status": "UNKNOWN_ACCOUNT_STATUS",
        "isLiquidating": true,
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
|data|[PageDataAccount](#schemapagedataaccount)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataAccount">PageDataAccount</h2>

<a id="schemapagedataaccount"></a>
<a id="schema_PageDataAccount"></a>
<a id="tocSpagedataaccount"></a>
<a id="tocspagedataaccount"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "ethAddress": "string",
      "l2Key": "string",
      "l2KeyYCoordinate": "string",
      "clientAccountId": "string",
      "isSystemAccount": true,
      "defaultTradeSetting": {
        "isSetFeeRate": true,
        "takerFeeRate": "string",
        "makerFeeRate": "string",
        "isSetFeeDiscount": true,
        "takerFeeDiscount": "string",
        "makerFeeDiscount": "string",
        "isSetMaxLeverage": true,
        "maxLeverage": "string"
      },
      "contractIdToTradeSetting": {
        "property1": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        },
        "property2": {
          "isSetFeeRate": true,
          "takerFeeRate": "string",
          "makerFeeRate": "string",
          "isSetFeeDiscount": true,
          "takerFeeDiscount": "string",
          "makerFeeDiscount": "string",
          "isSetMaxLeverage": true,
          "maxLeverage": "string"
        }
      },
      "maxLeverageLimit": "string",
      "createOrderPerMinuteLimit": 0,
      "createOrderDelayMillis": 0,
      "extraType": "string",
      "extraDataJson": "string",
      "status": "UNKNOWN_ACCOUNT_STATUS",
      "isLiquidating": true,
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
|dataList|[[Account](#schemaaccount)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Result<List<Collateral>>">Result<List<Collateral>></h2>

<a id="schemaresult<list<collateral>>"></a>
<a id="schema_Result<List<Collateral>>"></a>
<a id="tocSresult<list<collateral>>"></a>
<a id="tocsresult<list<collateral>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "amount": "string",
      "legacyAmount": "string",
      "cumDepositAmount": "string",
      "cumWithdrawAmount": "string",
      "cumTransferInAmount": "string",
      "cumTransferOutAmount": "string",
      "cumPositionBuyAmount": "string",
      "cumPositionSellAmount": "string",
      "cumFillFeeAmount": "string",
      "cumFundingFeeAmount": "string",
      "cumFillFeeIncomeAmount": "string",
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
|data|[[Collateral](#schemacollateral)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Result<List<CollateralTransaction>>">Result<List<CollateralTransaction>></h2>

<a id="schemaresult<list<collateraltransaction>>"></a>
<a id="schema_Result<List<CollateralTransaction>>"></a>
<a id="tocSresult<list<collateraltransaction>>"></a>
<a id="tocsresult<list<collateraltransaction>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
      "deltaAmount": "string",
      "deltaLegacyAmount": "string",
      "beforeAmount": "string",
      "beforeLegacyAmount": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "depositId": "string",
      "withdrawId": "string",
      "transferInId": "string",
      "transferOutId": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "orderAccountId": "string",
      "positionContractId": "string",
      "positionTransactionId": "string",
      "forceWithdrawId": "string",
      "forceTradeId": "string",
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
|data|[[CollateralTransaction](#schemacollateraltransaction)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CollateralTransaction">CollateralTransaction</h2>

<a id="schemacollateraltransaction"></a>
<a id="schema_CollateralTransaction"></a>
<a id="tocScollateraltransaction"></a>
<a id="tocscollateraltransaction"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
  "deltaAmount": "string",
  "deltaLegacyAmount": "string",
  "beforeAmount": "string",
  "beforeLegacyAmount": "string",
  "fillCloseSize": "string",
  "fillCloseValue": "string",
  "fillCloseFee": "string",
  "fillOpenSize": "string",
  "fillOpenValue": "string",
  "fillOpenFee": "string",
  "fillPrice": "string",
  "liquidateFee": "string",
  "realizePnl": "string",
  "isLiquidate": true,
  "isDeleverage": true,
  "fundingTime": "string",
  "fundingRate": "string",
  "fundingIndexPrice": "string",
  "fundingOraclePrice": "string",
  "fundingPositionSize": "string",
  "depositId": "string",
  "withdrawId": "string",
  "transferInId": "string",
  "transferOutId": "string",
  "transferReason": "UNKNOWN_TRANSFER_REASON",
  "orderId": "string",
  "orderFillTransactionId": "string",
  "orderAccountId": "string",
  "positionContractId": "string",
  "positionTransactionId": "string",
  "forceWithdrawId": "string",
  "forceTradeId": "string",
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

抵押品变动明细

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||唯一标识|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||货币id|
|type|string|false|none||明细类型|
|deltaAmount|string(decimal)|false|none||抵押品变动数量|
|deltaLegacyAmount|string(decimal)|false|none||老式记账方式余额字段变动数量|
|beforeAmount|string(decimal)|false|none||变动前的抵押品数量|
|beforeLegacyAmount|string(decimal)|false|none||变动前的老式记账方式余额字段|
|fillCloseSize|string(decimal)|false|none||成交平仓数量 (正数为买入，负数为卖出)|
|fillCloseValue|string|false|none||成交平仓价值 (正数为买入，负数为卖出)|
|fillCloseFee|string|false|none||成交平仓手续费 (一般为零或负数)|
|fillOpenSize|string|false|none||成交开仓数量 (正数为买入，负数为卖出)|
|fillOpenValue|string|false|none||成交开仓价值 (正数为买入，负数为卖出)|
|fillOpenFee|string|false|none||成交开仓手续费 (一般为零或负数)|
|fillPrice|string(decimal)|false|none||成交价格 (非精确值，仅展示使用)|
|liquidateFee|string(decimal)|false|none||清算费 (强平费) (有平仓成交时存在。一般为零或负数)|
|realizePnl|string(decimal)|false|none||平仓已实现盈亏 (有平仓成交时存在。非精确值，仅展示使用)|
|isLiquidate|boolean|false|none||是否是强平成交|
|isDeleverage|boolean|false|none||是否是自动减仓成交|
|fundingTime|string(int64)|false|none||资金费率结算时间|
|fundingRate|string(decimal)|false|none||资金费率|
|fundingIndexPrice|string(decimal)|false|none||资金费率相关的指数价格|
|fundingOraclePrice|string(decimal)|false|none||资金费率相关的预言机价格|
|fundingPositionSize|string(decimal)|false|none||资金费用结算时仓位大小 (正数为多仓，负数为空仓)|
|depositId|string(int64)|false|none||当 type=DEPOSIT 时，此字段为关联的充值单id|
|withdrawId|string(int64)|false|none||当 type=WITHDRAW 时，此字段为关联的提现单id|
|transferInId|string(int64)|false|none||当 type=TRANSFER_IN 时，此字段为关联的转账转入单id|
|transferOutId|string(int64)|false|none||当 type=TRANSFER_OUT 时，此字段为关联的转账转出单id|
|transferReason|string|false|none||当 type=TRANSFER_IN/TRANSFER_OUT 时，此字段为转账原因|
|orderId|string(int64)|false|none||当 type=POSITION_BUY/POSITION_SELL/FILL_FEE_INCOME 时，此字段为关联的委托单id|
|orderFillTransactionId|string(int64)|false|none||当 type=POSITION_BUY/POSITION_SELL/FILL_FEE_INCOME 时，此字段为关联的委托单成交明细id|
|orderAccountId|string(int64)|false|none||当 type=FILL_FEE_INCOME 时，此字段为关联的委托单账户id|
|positionContractId|string(int64)|false|none||当 type=POSITION_BUY/POSITION_SELL/POSITION_FUNDING/FILL_FEE_INCOME 时，关联的仓位合约id|
|positionTransactionId|string(int64)|false|none||当 type=POSITION_BUY/POSITION_SELL/POSITION_FUNDING 时，此字段为关联的仓位流水id|
|forceWithdrawId|string|false|none||当 type=WITHDRAW 时，此字段为关联的强制提现单id|
|forceTradeId|string|false|none||当 type=POSITION_BUY/POSITION_SELL 时，此字段为关联的强制交易单id|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||附加数据，json格式，默认为空串|
|censorStatus|string|false|none||当前审查状态|
|censorTxId|string(int64)|false|none||审查处理序号。当 censor_status=CENSOR_SUCCESS/CENSOR_FAILURE/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED 时存在|
|censorTime|string(int64)|false|none||审查处理时间。当 censor_status=CENSOR_SUCCESS/CENSOR_FAILURE/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED 时存在|
|censorFailCode|string|false|none||审查失败错误码。当 censor_status=CENSOR_FAILURE 时存在|
|censorFailReason|string|false|none||审查失败原因。当 censor_status=CENSOR_FAILURE 时存在|
|l2TxId|string(int64)|false|none||l2推送交易id。当 censor_status=CENSOR_SUCCESS/L2_APPROVED/L2_REJECT/L2_REJECT_APPROVED 时存在|
|l2RejectTime|string(int64)|false|none||l2拒绝时间。当 censor_status=L2_REJECT/L2_REJECT_APPROVED 时存在|
|l2RejectCode|string|false|none||l2拒绝错误码。当 censor_status=L2_REJECT/L2_REJECT_APPROVED 时存在|
|l2RejectReason|string|false|none||l2拒绝原因。当 censor_status=L2_REJECT/L2_REJECT_APPROVED 时存在|
|l2ApprovedTime|string(int64)|false|none||l2批次验证时间。当 censor_status=L2_APPROVED/L2_REJECT_APPROVED 时存在|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|type|UNKNOWN_COLLATERAL_TRANSACTION_TYPE|
|type|DEPOSIT|
|type|WITHDRAW|
|type|TRANSFER_IN|
|type|TRANSFER_OUT|
|type|POSITION_BUY|
|type|POSITION_SELL|
|type|POSITION_FUNDING|
|type|FILL_FEE_INCOME|
|type|BUG_FIX_COLLATERAL_TRANSACTION_TYPE|
|type|UNRECOGNIZED|
|transferReason|UNKNOWN_TRANSFER_REASON|
|transferReason|USER_TRANSFER|
|transferReason|FAST_WITHDRAW|
|transferReason|CROSS_DEPOSIT|
|transferReason|CROSS_WITHDRAW|
|transferReason|UNRECOGNIZED|
|censorStatus|UNKNOWN_TRANSACTION_STATUS|
|censorStatus|INIT|
|censorStatus|CENSOR_SUCCESS|
|censorStatus|CENSOR_FAILURE|
|censorStatus|L2_APPROVED|
|censorStatus|L2_REJECT|
|censorStatus|L2_REJECT_APPROVED|
|censorStatus|UNRECOGNIZED|

<h2 id="tocS_Result<PageData<CollateralTransaction>>">Result<PageData<CollateralTransaction>></h2>

<a id="schemaresult<pagedata<collateraltransaction>>"></a>
<a id="schema_Result<PageData<CollateralTransaction>>"></a>
<a id="tocSresult<pagedata<collateraltransaction>>"></a>
<a id="tocsresult<pagedata<collateraltransaction>>"></a>

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
        "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
        "deltaAmount": "string",
        "deltaLegacyAmount": "string",
        "beforeAmount": "string",
        "beforeLegacyAmount": "string",
        "fillCloseSize": "string",
        "fillCloseValue": "string",
        "fillCloseFee": "string",
        "fillOpenSize": "string",
        "fillOpenValue": "string",
        "fillOpenFee": "string",
        "fillPrice": "string",
        "liquidateFee": "string",
        "realizePnl": "string",
        "isLiquidate": true,
        "isDeleverage": true,
        "fundingTime": "string",
        "fundingRate": "string",
        "fundingIndexPrice": "string",
        "fundingOraclePrice": "string",
        "fundingPositionSize": "string",
        "depositId": "string",
        "withdrawId": "string",
        "transferInId": "string",
        "transferOutId": "string",
        "transferReason": "UNKNOWN_TRANSFER_REASON",
        "orderId": "string",
        "orderFillTransactionId": "string",
        "orderAccountId": "string",
        "positionContractId": "string",
        "positionTransactionId": "string",
        "forceWithdrawId": "string",
        "forceTradeId": "string",
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
|data|[PageDataCollateralTransaction](#schemapagedatacollateraltransaction)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataCollateralTransaction">PageDataCollateralTransaction</h2>

<a id="schemapagedatacollateraltransaction"></a>
<a id="schema_PageDataCollateralTransaction"></a>
<a id="tocSpagedatacollateraltransaction"></a>
<a id="tocspagedatacollateraltransaction"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "type": "UNKNOWN_COLLATERAL_TRANSACTION_TYPE",
      "deltaAmount": "string",
      "deltaLegacyAmount": "string",
      "beforeAmount": "string",
      "beforeLegacyAmount": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "depositId": "string",
      "withdrawId": "string",
      "transferInId": "string",
      "transferOutId": "string",
      "transferReason": "UNKNOWN_TRANSFER_REASON",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "orderAccountId": "string",
      "positionContractId": "string",
      "positionTransactionId": "string",
      "forceWithdrawId": "string",
      "forceTradeId": "string",
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
|dataList|[[CollateralTransaction](#schemacollateraltransaction)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Result<List<Position>>">Result<List<Position>></h2>

<a id="schemaresult<list<position>>"></a>
<a id="schema_Result<List<Position>>"></a>
<a id="tocSresult<list<position>>"></a>
<a id="tocsresult<list<position>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "openSize": "string",
      "openValue": "string",
      "openFee": "string",
      "fundingFee": "string",
      "longTermCount": 0,
      "longTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "longTermCreatedTime": "string",
      "longTermUpdatedTime": "string",
      "shortTermCount": 0,
      "shortTermStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTermCreatedTime": "string",
      "shortTermUpdatedTime": "string",
      "longTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
      "shortTotalStat": {
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string"
      },
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
|data|[[Position](#schemaposition)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Result<PageData<PositionTerm>>">Result<PageData<PositionTerm>></h2>

<a id="schemaresult<pagedata<positionterm>>"></a>
<a id="schema_Result<PageData<PositionTerm>>"></a>
<a id="tocSresult<pagedata<positionterm>>"></a>
<a id="tocsresult<pagedata<positionterm>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "userId": "string",
        "accountId": "string",
        "coinId": "string",
        "contractId": "string",
        "termCount": 0,
        "cumOpenSize": "string",
        "cumOpenValue": "string",
        "cumOpenFee": "string",
        "cumCloseSize": "string",
        "cumCloseValue": "string",
        "cumCloseFee": "string",
        "cumFundingFee": "string",
        "cumLiquidateFee": "string",
        "createdTime": "string",
        "updatedTime": "string",
        "currentLeverage": "string"
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
|data|[PageDataPositionTerm](#schemapagedatapositionterm)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataPositionTerm">PageDataPositionTerm</h2>

<a id="schemapagedatapositionterm"></a>
<a id="schema_PageDataPositionTerm"></a>
<a id="tocSpagedatapositionterm"></a>
<a id="tocspagedatapositionterm"></a>

```json
{
  "dataList": [
    {
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "termCount": 0,
      "cumOpenSize": "string",
      "cumOpenValue": "string",
      "cumOpenFee": "string",
      "cumCloseSize": "string",
      "cumCloseValue": "string",
      "cumCloseFee": "string",
      "cumFundingFee": "string",
      "cumLiquidateFee": "string",
      "createdTime": "string",
      "updatedTime": "string",
      "currentLeverage": "string"
    }
  ],
  "nextPageOffsetData": "string"
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[PositionTerm](#schemapositionterm)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_PositionTerm">PositionTerm</h2>

<a id="schemapositionterm"></a>
<a id="schema_PositionTerm"></a>
<a id="tocSpositionterm"></a>
<a id="tocspositionterm"></a>

```json
{
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "termCount": 0,
  "cumOpenSize": "string",
  "cumOpenValue": "string",
  "cumOpenFee": "string",
  "cumCloseSize": "string",
  "cumCloseValue": "string",
  "cumCloseFee": "string",
  "cumFundingFee": "string",
  "cumLiquidateFee": "string",
  "createdTime": "string",
  "updatedTime": "string",
  "currentLeverage": "string"
}

```

仓位term信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string|false|none||所属用户id|
|accountId|string|false|none||所属账户id|
|coinId|string|false|none||所属抵押品币种id|
|contractId|string|false|none||所属合约id|
|termCount|integer(int32)|false|none||term次数。从1开始，每次完全平仓后开仓会加一。|
|cumOpenSize|string|false|none||累计开仓数量|
|cumOpenValue|string|false|none||累计开仓价值|
|cumOpenFee|string|false|none||累计开仓费用|
|cumCloseSize|string|false|none||累计平仓数量|
|cumCloseValue|string|false|none||累计平仓价值|
|cumCloseFee|string|false|none||累计平仓费用|
|cumFundingFee|string|false|none||累计已结算的资金费用|
|cumLiquidateFee|string|false|none||累计清算费用|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|
|currentLeverage|string|false|none||平仓时杠杆倍数|

<h2 id="tocS_Result<List<PositionTransaction>>">Result<List<PositionTransaction>></h2>

<a id="schemaresult<list<positiontransaction>>"></a>
<a id="schema_Result<List<PositionTransaction>>"></a>
<a id="tocSresult<list<positiontransaction>>"></a>
<a id="tocsresult<list<positiontransaction>>"></a>

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
      "type": "UNKNOWN_POSITION_TRANSACTION_TYPE",
      "deltaOpenSize": "string",
      "deltaOpenValue": "string",
      "deltaOpenFee": "string",
      "deltaFundingFee": "string",
      "beforeOpenSize": "string",
      "beforeOpenValue": "string",
      "beforeOpenFee": "string",
      "beforeFundingFee": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "collateralTransactionId": "string",
      "forceTradeId": "string",
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
|data|[[PositionTransaction](#schemapositiontransaction)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PositionTransaction">PositionTransaction</h2>

<a id="schemapositiontransaction"></a>
<a id="schema_PositionTransaction"></a>
<a id="tocSpositiontransaction"></a>
<a id="tocspositiontransaction"></a>

```json
{
  "id": "string",
  "userId": "string",
  "accountId": "string",
  "coinId": "string",
  "contractId": "string",
  "type": "UNKNOWN_POSITION_TRANSACTION_TYPE",
  "deltaOpenSize": "string",
  "deltaOpenValue": "string",
  "deltaOpenFee": "string",
  "deltaFundingFee": "string",
  "beforeOpenSize": "string",
  "beforeOpenValue": "string",
  "beforeOpenFee": "string",
  "beforeFundingFee": "string",
  "fillCloseSize": "string",
  "fillCloseValue": "string",
  "fillCloseFee": "string",
  "fillOpenSize": "string",
  "fillOpenValue": "string",
  "fillOpenFee": "string",
  "fillPrice": "string",
  "liquidateFee": "string",
  "realizePnl": "string",
  "isLiquidate": true,
  "isDeleverage": true,
  "fundingTime": "string",
  "fundingRate": "string",
  "fundingIndexPrice": "string",
  "fundingOraclePrice": "string",
  "fundingPositionSize": "string",
  "orderId": "string",
  "orderFillTransactionId": "string",
  "collateralTransactionId": "string",
  "forceTradeId": "string",
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

永续合约持仓变动明细

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||唯一标识|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|contractId|string(int64)|false|none||所属合约id|
|type|string|false|none||明细类型|
|deltaOpenSize|string|false|none||持有数量变动值|
|deltaOpenValue|string|false|none||开仓价值变动值|
|deltaOpenFee|string|false|none||开仓手续费用变动值|
|deltaFundingFee|string|false|none||资金费用变动值|
|beforeOpenSize|string|false|none||变动前的持有数量|
|beforeOpenValue|string|false|none||变动前的开仓价值|
|beforeOpenFee|string|false|none||变动前的开仓手续费用|
|beforeFundingFee|string|false|none||变动前的资金费用|
|fillCloseSize|string|false|none||成交平仓数量 (正数为买入，负数为卖出)|
|fillCloseValue|string|false|none||成交平仓价值 (正数为买入，负数为卖出)|
|fillCloseFee|string|false|none||成交平仓手续费 (一般为零或负数)|
|fillOpenSize|string|false|none||成交开仓数量 (正数为买入，负数为卖出)|
|fillOpenValue|string|false|none||成交开仓价值 (正数为买入，负数为卖出)|
|fillOpenFee|string|false|none||成交开仓手续费 (一般为零或负数)|
|fillPrice|string|false|none||成交价格 (非精确值，仅展示使用)|
|liquidateFee|string|false|none||清算费 (强平费) (有平仓成交时存在。一般为零或负数)|
|realizePnl|string|false|none||已实现盈亏 (有平仓成交时存在。非精确值，仅展示使用)|
|isLiquidate|boolean|false|none||是否是强平成交|
|isDeleverage|boolean|false|none||是否是自动减仓成交|
|fundingTime|string(int64)|false|none||资金费率结算时间|
|fundingRate|string|false|none||资金费率|
|fundingIndexPrice|string|false|none||资金费率相关的指数价格|
|fundingOraclePrice|string|false|none||资金费率相关的预言机价格|
|fundingPositionSize|string|false|none||资金费用结算时仓位大小 (正数为多仓，负数为空仓)|
|orderId|string(int64)|false|none||此字段为关联的委托单id|
|orderFillTransactionId|string(int64)|false|none||此字段为关联的委托单成交交易id|
|collateralTransactionId|string(int64)|false|none||关联的抵押品明细id|
|forceTradeId|string|false|none||此字段为关联的强制交易id|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||附加数据，json格式，默认为空串|
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
|type|UNKNOWN_POSITION_TRANSACTION_TYPE|
|type|BUY_POSITION|
|type|SELL_POSITION|
|type|SETTLE_FUNDING_FEE|
|type|BUG_FIX_POSITION_TRANSACTION_TYPE|
|type|UNRECOGNIZED|
|censorStatus|UNKNOWN_TRANSACTION_STATUS|
|censorStatus|INIT|
|censorStatus|CENSOR_SUCCESS|
|censorStatus|CENSOR_FAILURE|
|censorStatus|L2_APPROVED|
|censorStatus|L2_REJECT|
|censorStatus|L2_REJECT_APPROVED|
|censorStatus|UNRECOGNIZED|

<h2 id="tocS_Result<PageData<PositionTransaction>>">Result<PageData<PositionTransaction>></h2>

<a id="schemaresult<pagedata<positiontransaction>>"></a>
<a id="schema_Result<PageData<PositionTransaction>>"></a>
<a id="tocSresult<pagedata<positiontransaction>>"></a>
<a id="tocsresult<pagedata<positiontransaction>>"></a>

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
        "type": "UNKNOWN_POSITION_TRANSACTION_TYPE",
        "deltaOpenSize": "string",
        "deltaOpenValue": "string",
        "deltaOpenFee": "string",
        "deltaFundingFee": "string",
        "beforeOpenSize": "string",
        "beforeOpenValue": "string",
        "beforeOpenFee": "string",
        "beforeFundingFee": "string",
        "fillCloseSize": "string",
        "fillCloseValue": "string",
        "fillCloseFee": "string",
        "fillOpenSize": "string",
        "fillOpenValue": "string",
        "fillOpenFee": "string",
        "fillPrice": "string",
        "liquidateFee": "string",
        "realizePnl": "string",
        "isLiquidate": true,
        "isDeleverage": true,
        "fundingTime": "string",
        "fundingRate": "string",
        "fundingIndexPrice": "string",
        "fundingOraclePrice": "string",
        "fundingPositionSize": "string",
        "orderId": "string",
        "orderFillTransactionId": "string",
        "collateralTransactionId": "string",
        "forceTradeId": "string",
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
|data|[PageDataPositionTransaction](#schemapagedatapositiontransaction)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataPositionTransaction">PageDataPositionTransaction</h2>

<a id="schemapagedatapositiontransaction"></a>
<a id="schema_PageDataPositionTransaction"></a>
<a id="tocSpagedatapositiontransaction"></a>
<a id="tocspagedatapositiontransaction"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "accountId": "string",
      "coinId": "string",
      "contractId": "string",
      "type": "UNKNOWN_POSITION_TRANSACTION_TYPE",
      "deltaOpenSize": "string",
      "deltaOpenValue": "string",
      "deltaOpenFee": "string",
      "deltaFundingFee": "string",
      "beforeOpenSize": "string",
      "beforeOpenValue": "string",
      "beforeOpenFee": "string",
      "beforeFundingFee": "string",
      "fillCloseSize": "string",
      "fillCloseValue": "string",
      "fillCloseFee": "string",
      "fillOpenSize": "string",
      "fillOpenValue": "string",
      "fillOpenFee": "string",
      "fillPrice": "string",
      "liquidateFee": "string",
      "realizePnl": "string",
      "isLiquidate": true,
      "isDeleverage": true,
      "fundingTime": "string",
      "fundingRate": "string",
      "fundingIndexPrice": "string",
      "fundingOraclePrice": "string",
      "fundingPositionSize": "string",
      "orderId": "string",
      "orderFillTransactionId": "string",
      "collateralTransactionId": "string",
      "forceTradeId": "string",
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
|dataList|[[PositionTransaction](#schemapositiontransaction)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Result<RegisterAccount>">Result<RegisterAccount></h2>

<a id="schemaresult<registeraccount>"></a>
<a id="schema_Result<RegisterAccount>"></a>
<a id="tocSresult<registeraccount>"></a>
<a id="tocsresult<registeraccount>"></a>

```json
{
  "code": "string",
  "data": {
    "accountId": "string"
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
|data|[RegisterAccount](#schemaregisteraccount)|false|none||注册账户-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_RegisterAccount">RegisterAccount</h2>

<a id="schemaregisteraccount"></a>
<a id="schema_RegisterAccount"></a>
<a id="tocSregisteraccount"></a>
<a id="tocsregisteraccount"></a>

```json
{
  "accountId": "string"
}

```

注册账户-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|

<h2 id="tocS_RegisterAccountParam">RegisterAccountParam</h2>

<a id="schemaregisteraccountparam"></a>
<a id="schema_RegisterAccountParam"></a>
<a id="tocSregisteraccountparam"></a>
<a id="tocsregisteraccountparam"></a>

```json
{
  "l2Key": "string",
  "l2KeyYCoordinate": "string",
  "clientAccountId": "string"
}

```

注册账户-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|l2Key|string|false|none||L2上的账户key，保证全局唯一。对应starkEx中的starkKey。bigint for hex str|
|l2KeyYCoordinate|string|false|none||只用于验证 l2Signature 是否ok。不返回给C端用户。bigint for hex str|
|clientAccountId|string|false|none||客户端账户id, 用于幂等性校验|

<h2 id="tocS_UpdateFeeSettingParam">UpdateFeeSettingParam</h2>

<a id="schemaupdatefeesettingparam"></a>
<a id="schema_UpdateFeeSettingParam"></a>
<a id="tocSupdatefeesettingparam"></a>
<a id="tocsupdatefeesettingparam"></a>

```json
{
  "accountId": "string",
  "contractId": "string",
  "isSetFeeRate": true,
  "takerFeeRate": "string",
  "makerFeeRate": "string",
  "isSetFeeDiscount": true,
  "takerFeeDiscount": "string",
  "makerFeeDiscount": "string"
}

```

更新账户交易费率设置-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|contractId|string(int64)|false|none||合约id，如果为0的话，会更改账户默认fee设置|
|isSetFeeRate|boolean|false|none||是否设置费率(具体值)|
|takerFeeRate|string|false|none||taker费率，取值范围 [0, 1)，仅当 is_set_fee_rate=true 时有效|
|makerFeeRate|string|false|none||maker费率，取值范围 [0, 1)，仅当 is_set_fee_rate=true 时有效|
|isSetFeeDiscount|boolean|false|none||是否设置费率折扣|
|takerFeeDiscount|string|false|none||taker费率折扣|
|makerFeeDiscount|string|false|none||maker费率折扣|

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

<h2 id="tocS_Result<Void>">Result<Void></h2>

<a id="schemaresult<void>"></a>
<a id="schema_Result<Void>"></a>
<a id="tocSresult<void>"></a>
<a id="tocsresult<void>"></a>

```json
{
  "code": "string",
  "data": {},
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
|data|object|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_UpdateLeverageSettingParam">UpdateLeverageSettingParam</h2>

<a id="schemaupdateleveragesettingparam"></a>
<a id="schema_UpdateLeverageSettingParam"></a>
<a id="tocSupdateleveragesettingparam"></a>
<a id="tocsupdateleveragesettingparam"></a>

```json
{
  "accountId": "string",
  "contractId": "string",
  "leverage": "string"
}

```

更新账户交易杠杆设置-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|contractId|string(int64)|false|none||合约id，如果为0的话，会更改账户默认fee设置|
|leverage|string|false|none||杠杆倍数|

