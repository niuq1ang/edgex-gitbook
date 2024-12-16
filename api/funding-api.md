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

# 02.UserPublicApi

<a id="opIdverifyEmail"></a>

## POST 验证邮箱

POST /api/v1/public/user/verifyEmail

> Body 请求参数

```json
{
  "userId": "string",
  "token": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[VerifyEmailParam](#schemaverifyemailparam)| 否 |none|

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

<a id="opIdonboardSite"></a>

## POST 用户登录站点

POST /api/v1/public/user/onboardSite

> Body 请求参数

```json
{
  "ethAddress": "string",
  "onlySignOn": "string",
  "param": "string",
  "signature": "string",
  "l2Key": "string",
  "l2KeyYCoordinate": "string",
  "clientAccountId": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[OnboardSiteParam](#schemaonboardsiteparam)| 否 |none|

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

<a id="opIdgetAppScanSecret"></a>

## GET 获取AppScanSecret

GET /api/v1/public/user/getAppScanSecret

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|token|query|string| 否 |token|

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

<a id="opIdcheckUserExist"></a>

## GET 判断用户是否存在

GET /api/v1/public/user/checkUserExist

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|ethAddress|query|string| 否 |ETH地址|

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

# 00.StarkExPublicApi

<a id="opIdreceiveAlternativeTx"></a>

## POST 通知交易拒绝

POST /api/v1/public/starkex/receiveAlternativeTx

> Body 请求参数

```json
{
  "tx_id": 0,
  "reason_code": "string",
  "reason_msg": "string",
  "tx": {}
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 是 |none|
|body|body|[NotifyTxRejectParam](#schemanotifytxrejectparam)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "alt_txs": [
    {}
  ]
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[NotifyTxRejectResult](#schemanotifytxrejectresult)|

# 01.IndexPublicApi

<a id="opIdforcePushPrice"></a>

## POST 按照某个指定价格作为预言机价格推送(仅测试时使用)

POST /api/v1/public/index/forcePushPrice

> Body 请求参数

```json
{
  "contractId": "string",
  "price": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[ForcePushPriceParam](#schemaforcepushpriceparam)| 否 |none|

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

<a id="opIdgetIndexPriceConfig"></a>

## GET 根据合约id查询指数价格配置

GET /api/v1/public/index/getIndexPriceConfig

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractIdList|query|string| 否 |指定的合约id|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "indexPriceExchangeInfoList": [
        {
          "exchangeName": "string",
          "exchangeQuote": "string",
          "weight": "string"
        }
      ]
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

# 08.UserPrivateApi

<a id="opIdupdateUser"></a>

## POST 更新用户信息

POST /api/v1/private/user/updateUser

> Body 请求参数

```json
{
  "nickname": "string",
  "email": "string",
  "country": "string",
  "language": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[UpdateUserParam](#schemaupdateuserparam)| 否 |none|

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

<a id="opIdupdateUserPreference"></a>

## POST 更新用户设置

POST /api/v1/private/user/updateUserPreference

> Body 请求参数

```json
{
  "isSharingEthAddress": true,
  "isSharingNickname": true,
  "isEmailNotifyGeneralEnable": true,
  "isEmailNotifyTradingEnable": true,
  "isEmailNotifyAccountEnable": true,
  "isAppNotifyTradingEnable": true
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[UpdateUserPreferenceParam](#schemaupdateuserpreferenceparam)| 否 |none|

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

<a id="opIdsendEmailVerification"></a>

## POST (重新)发送邮箱验证

POST /api/v1/private/user/sendEmailVerification

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

<a id="opIdreadSiteMessage"></a>

## POST 标识阅读站内信消息

POST /api/v1/private/user/readSiteMessage

> Body 请求参数

```json
{
  "messageIdList": [
    "string"
  ]
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[ReadSiteMessageParam](#schemareadsitemessageparam)| 否 |none|

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

<a id="opIdcreateAppScanSecret"></a>

## POST 创建AppScanSecret

POST /api/v1/private/user/createAppScanSecret

> Body 请求参数

```json
{
  "expireTime": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateAppScanSecretParam](#schemacreateappscansecretparam)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {
    "token": "string",
    "secret": "string"
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

<a id="opIdgetUserById"></a>

## GET 根据id获取用户信息

GET /api/v1/private/user/getUser

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

<a id="opIdgetUserPreference"></a>

## GET 根据id获取用户设置

GET /api/v1/private/user/getUserPreference

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

<a id="opIdgetUserInfo"></a>

## GET 根据id获取用户信息和用户设置设置

GET /api/v1/private/user/getUserInfo

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {
    "user": {
      "id": "string",
      "ethAddress": "string",
      "nickname": "string",
      "email": "string",
      "isEmailVerified": true,
      "country": "string",
      "language": "string",
      "avatarUrl": "string",
      "avatarBorderUrl": "string",
      "createdTime": "string",
      "updatedTime": "string"
    },
    "userPreference": {
      "userId": "string",
      "isSharingEthAddress": true,
      "isSharingNickname": true,
      "isEmailNotifyGeneralEnable": true,
      "isEmailNotifyTradingEnable": true,
      "isEmailNotifyAccountEnable": true,
      "isAppNotifyTradingEnable": true,
      "createdTime": "string",
      "updatedTime": "string"
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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetSiteMessagePage"></a>

## GET 分页获取站内信

GET /api/v1/private/user/getSiteMessagePage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterBusinessTypeList|query|string| 否 |站内信类型(小类)，先忽略，有用的时候再说|
|filterNotifyCategoryList|query|string| 否 |站内信类型(大类)，不填查询全部|
|unread|query|string| 否 |true:获取未读列表,其他 获取全部|

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

<a id="opIdgetFaucetCoinClaimPage"></a>

## GET 分页获取水龙头领取记录

GET /api/v1/private/user/getFaucetCoinClaimPage

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

<a id="opIdclaimFaucetCoin"></a>

## GET 领取水龙头体验代币

GET /api/v1/private/user/claimFaucetCoin

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

<a id="opIdcheckUserNicknameExist"></a>

## GET 检查用户昵称是否存在

GET /api/v1/private/user/checkUserNicknameExist

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|nickname|query|string| 是 |昵称|

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

# 04.OrderPrivateApi

<a id="opIdgetMaxCreateOrderSize"></a>

## POST 获取最大下单数量

POST /api/v1/private/order/getMaxCreateOrderSize

> Body 请求参数

```json
{
  "accountId": "string",
  "contractId": "string",
  "price": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[GetMaxCreateOrderSizeParam](#schemagetmaxcreateordersizeparam)| 否 |none|

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

<a id="opIdcreateOrder"></a>

## POST 创建委托单

POST /api/v1/private/order/createOrder

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CreateOrderParam](#schemacreateorderparam)| 否 |none|

> 返回示例

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdcancelOrderById"></a>

## POST 根据委托单id取消委托单

POST /api/v1/private/order/cancelOrderById

> Body 请求参数

```json
{
  "accountId": "string",
  "orderIdList": [
    "string"
  ]
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CancelOrderByIdParam](#schemacancelorderbyidparam)| 否 |none|

> 返回示例

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdcancelOrderByClientOrderId"></a>

## POST 根据clientId取消委托单

POST /api/v1/private/order/cancelOrderByClientOrderId

> Body 请求参数

```json
{
  "accountId": "string",
  "clientOrderIdList": [
    "string"
  ]
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CancelOrderByClientOrderIdParam](#schemacancelorderbyclientorderidparam)| 否 |none|

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

<a id="opIdcancelAllOrder"></a>

## POST 取消账户下所有委托单

POST /api/v1/private/order/cancelAllOrder

> Body 请求参数

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

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|[CancelAllOrderParam](#schemacancelallorderparam)| 否 |none|

> 返回示例

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetOrderById"></a>

## GET 根据账户id和委托单id批量获取委托单

GET /api/v1/private/order/getOrderById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|orderIdList|query|string| 否 |委托单id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetOrderByClientOrderId"></a>

## GET 根据客户id批量获取委托单

GET /api/v1/private/order/getOrderByClientOrderId

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|clientOrderIdList|query|string| 否 |客户端自定义委托单id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetHistoryOrderPage"></a>

## GET 根据账户id翻页获取委托单

GET /api/v1/private/order/getHistoryOrderPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的委托单，如果为空则获取所有抵押品coinId的委托单|
|filterContractIdList|query|string| 否 |过滤获取指定合约的委托单；如果为空的话获取所有合约委托单|
|filterTypeList|query|string| 否 |过滤获取指定类型的委托单，不填的话所有类型委托单|
|filterStatusList|query|string| 否 |过滤获取指定状态的委托单，不填的话所有状态委托单|
|filterIsLiquidateList|query|string| 否 |过滤获取指定是否为清算的委托单，不填的话所有委托单|
|filterIsDeleverageList|query|string| 否 |过滤获取指定是否为减仓的委托单，不填的话所有委托单|
|filterIsPositionTpslList|query|string| 否 |过滤获取指定是否为仓位止盈止损单，不填的话所有委托单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的委托单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 | 过滤获取指定结束时间创建的委托单 (不包含)，不填或者为0的话就到最近|

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

<a id="opIdgetHistoryOrderFillTransactionPage"></a>

## GET 根据账户id和委托单ids批量获取成交单

GET /api/v1/private/order/getHistoryOrderFillTransactionPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于100|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的成交明细，如果为空则获取所有抵押品coinId的成交明细|
|filterContractIdList|query|string| 否 |过滤获取指定合约的委托成交明细；如果为空的话获取所有合约委托成交明细|
|filterOrderIdList|query|string| 否 |过滤获取指定委托单的成交明细；如果为空的话获取所有委托单的委托成交明细|
|filterIsLiquidateList|query|string| 否 |过滤获取指定是否为清算的委托单，不填的话所有委托单|
|filterIsDeleverageList|query|string| 否 |过滤获取指定是否为减仓的委托单，不填的话所有委托单|
|filterIsPositionTpslList|query|string| 否 |过滤获取指定是否为仓位止盈止损单，不填的话所有委托单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的委托单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 | 过滤获取指定结束时间创建的委托单 (不包含)，不填或者为0的话就到最近|

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

<a id="opIdgetHistoryOrderFillTransactionById"></a>

## GET 根据账户id和委托成交明细id批量获取委托成交明细

GET /api/v1/private/order/getHistoryOrderFillTransactionById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|orderFillTransactionIdList|query|string| 否 |委托成交明细id|

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

<a id="opIdgetHistoryOrderById"></a>

## GET 根据账户id和委托单id批量获取委托单

GET /api/v1/private/order/getHistoryOrderById

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|orderIdList|query|string| 否 |委托单id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetHistoryOrderByClientOrderId"></a>

## GET 根据账户id和委托单id批量获取委托单

GET /api/v1/private/order/getHistoryOrderByClientOrderId

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|clientOrderIdList|query|string| 否 |委托单 client order id|

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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

<a id="opIdgetActiveOrderPage"></a>

## GET 分页获取账户下活动的委托单

GET /api/v1/private/order/getActiveOrderPage

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|accountId|query|string| 否 |账户id|
|size|query|string| 否 |获取数量。必须大于0且小于等于200|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterCoinIdList|query|string| 否 |过滤获取对应抵押品coinId对应的活动委托单，如果为空则获取所有抵押品coinId的活动委托单|
|filterContractIdList|query|string| 否 |过滤获取对应合约的活动委托单，如果为空则获取所有合约的活动委托单|
|filterTypeList|query|string| 否 |过滤获取指定类型的委托单，不填的话所有类型委托单|
|filterStatusList|query|string| 否 |过滤获取指定状态的委托单，不填的话所有状态委托单|
|filterIsLiquidateList|query|string| 否 |过滤获取指定是否为清算的委托单，不填的话所有委托单|
|filterIsDeleverageList|query|string| 否 |过滤获取指定是否为减仓的委托单，不填的话所有委托单|
|filterIsPositionTpslList|query|string| 否 |过滤获取指定是否为仓位止盈止损单，不填的话所有委托单|
|filterStartCreatedTimeInclusive|query|string| 否 |过滤获取指定开始时间创建的委托单 (包含)，不填或者为0的话就从最早开始|
|filterEndCreatedTimeExclusive|query|string| 否 |过滤获取指定结束时间创建的委托单 (不包含)，不填或者为0的话就到最近|

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

# 01.QuotePublicApi

<a id="opIdgetTicketSummary"></a>

## GET 获取行情汇总

GET /api/v1/public/quote/getTicketSummary

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|period|query|string| 否 |汇总周期|

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

<a id="opIdgetTicker"></a>

## GET 查询24小时行情

GET /api/v1/public/quote/getTicker

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractId|query|string| 否 |合约id|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "contractName": "string",
      "priceChange": "string",
      "priceChangePercent": "string",
      "trades": "string",
      "size": "string",
      "value": "string",
      "high": "string",
      "low": "string",
      "open": "string",
      "close": "string",
      "highTime": "string",
      "lowTime": "string",
      "startTime": "string",
      "endTime": "string",
      "lastPrice": "string",
      "indexPrice": "string",
      "oraclePrice": "string",
      "openInterest": "string",
      "fundingRate": "string",
      "fundingTime": "string",
      "nextFundingTime": "string"
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

<a id="opIdgetStatDayTrade"></a>

## GET 获取日交易统计

GET /api/v1/public/quote/getStatDayTrade

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|startDayTimeInclusive|query|string| 否 |过滤获取指定开始时间的交易统计信息|
|endDayTimeExclusive|query|string| 否 | 过滤获取指定结束时间的日交易统计信息|

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

<a id="opIdgetMultiContractKline"></a>

## GET 查询多合约定量K线

GET /api/v1/public/quote/getMultiContractKline

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractIdList|query|string| 否 |合约id集合|
|priceType|query|string| 否 |价格类型|
|klineType|query|string| 否 |K线类型|
|size|query|string| 否 |获取数量。必须大于0且小于等于200|
|filterBeginKlineTimeInclusive|query|string| 否 |查询开始时间（如果为0表示从当前时间）按照时间倒序向前查询返回|
|filterEndKlineTimeExclusive|query|string| 否 |查询结束时间|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "klineList": [
        {
          "klineId": "string",
          "contractId": "string",
          "contractName": "string",
          "klineType": "UNKNOWN_KLINE_TYPE",
          "klineTime": "string",
          "priceType": "UNKNOWN_PRICE_TYPE",
          "trades": "string",
          "size": "string",
          "value": "string",
          "high": "string",
          "low": "string",
          "open": "string",
          "close": "string",
          "makerBuySize": "string",
          "makerBuyValue": "string"
        }
      ]
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

<a id="opIdgetKline"></a>

## GET 查询K线

GET /api/v1/public/quote/getKline

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractId|query|string| 否 |合约id|
|priceType|query|string| 否 |价格类型|
|klineType|query|string| 否 |K线类型|
|size|query|string| 否 |获取数量。必须大于0且小于等于1000|
|offsetData|query|string| 否 |翻页获取偏移。如果不填或者为空串，则获取第一页|
|filterBeginKlineTimeInclusive|query|string| 否 |查询开始时间（如果为0表示从当前时间）按照时间倒序向前查询返回|
|filterEndKlineTimeExclusive|query|string| 否 |查询结束时间|

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

<a id="opIdgetExchangeLongShortRatio"></a>

## GET 获取日交易统计

GET /api/v1/public/quote/getExchangeLongShortRatio

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|range|query|string| 否 |如果为空的话，默认返回 range 最小的数据|
|filterContractIdList|query|string| 否 |如果为空的话，默认返回所有合约数据|
|filterExchangeList|query|string| 否 |如果为空的话，默认返回所有交易所数据|

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

<a id="opIdgetDepth"></a>

## GET 查询盘口深度

GET /api/v1/public/quote/getDepth

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractId|query|string| 否 |合约id|
|level|query|string| 否 |深度档位 目前有15档和200档|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": [
    {
      "startVersion": "string",
      "endVersion": "string",
      "level": 0,
      "contractId": "string",
      "contractName": "string",
      "asks": [
        {
          "price": "string",
          "size": "string"
        }
      ],
      "bids": [
        {
          "price": "string",
          "size": "string"
        }
      ],
      "depthType": "UNKNOWN_DEPTH_TYPE"
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

<a id="opIdgetAccurateOpenInterest"></a>

## GET 获取精确OpenInterest

GET /api/v1/public/quote/getAccurateOpenInterest

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|contractIdList|query|string| 否 |合约id集合|

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

# 00.MetaDataPublicApi

<a id="opIdgetServerTime"></a>

## GET 获取服务器时间

GET /api/v1/public/meta/getServerTime

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

<a id="opIdgetMetaData"></a>

## GET 获取元信息数据

GET /api/v1/public/meta/getMetaData

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

# CMCPublicApi

<a id="opIdgetOrderBook"></a>

## GET Endpoint B3 (Order book)

GET /api/v1/public/cmc/getOrderBook

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

<a id="opIdgetContracts"></a>

## GET Endpoint B1 (Contracts)

GET /api/v1/public/cmc/getContracts

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

<a id="opIdgetContractSpecifications"></a>

## GET Endpoint B2  (Contract specifications)

GET /api/v1/public/cmc/getContractSpecifications

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

# 00.AppPublicApi

<a id="opIdgetAppUpdate"></a>

## GET 获取APP升级信息

GET /api/v1/public/app/checkAppUpdate

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|platform|query|string| 否 |客户端类型. 例如 Android / iOS|
|language|query|string| 否 |客户端请求语言. 例如 zh-CN / en-US|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {
    "latestVersion": "string",
    "downloadUrl": "string",
    "marketUrl": "string",
    "description": "string",
    "beForceUpdate": true,
    "beUpdate": true
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

# 01.1inchPublicController

<a id="opIdgetQuota"></a>

## GET 获取币对兑换汇率

GET /api/v1/public/1inch/getQuota

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|chainId|query|string| 否 |链id|
|src|query|string| 否 |输入代币合约地址|
|dst|query|string| 否 |目标代币合约地址|
|amount|query|string| 否 |输入金额，带精度|

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

<a id="opIdgetAggregateExchangeData"></a>

## GET 获取币对兑换汇率

GET /api/v1/public/1inch/getAggregateExchangeData

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|chainId|query|string| 否 |链id|
|src|query|string| 否 |输入代币合约地址|
|dst|query|string| 否 |目标代币合约地址|
|amount|query|string| 否 |输入金额，带精度|
|slippage|query|string| 否 |滑点|
|from|query|string| 否 |资金池合约地址|
|receiver|query|string| 否 |资金池合约地址|
|disableEstimate|query|string| 否 |是否关闭链上模拟执行|

> 返回示例

> 200 Response

```json
{
  "code": "string",
  "data": {
    "toAmount": "string",
    "tx": {
      "from": "string",
      "to": "string",
      "data": "string",
      "value": "string",
      "gas": "string",
      "gasPrice": "string"
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

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|Inline|

### 返回数据结构

# **.内部测试使用

<a id="opIdcreateApiCredential"></a>

## GET 根据signature派生ApiCredential的验证接口

GET /api/createApiCredential

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|signature|query|string| 是 |none|

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

<h2 id="tocS_Result<GenerateApiCredentialBySignature>">Result<GenerateApiCredentialBySignature></h2>

<a id="schemaresult<generateapicredentialbysignature>"></a>
<a id="schema_Result<GenerateApiCredentialBySignature>"></a>
<a id="tocSresult<generateapicredentialbysignature>"></a>
<a id="tocsresult<generateapicredentialbysignature>"></a>

```json
{
  "code": "string",
  "data": {
    "apiKey": "string",
    "secret": "string",
    "passphrase": "string"
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
|data|[GenerateApiCredentialBySignature](#schemagenerateapicredentialbysignature)|false|none||调用接口的接口认证凭据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GenerateApiCredentialBySignature">GenerateApiCredentialBySignature</h2>

<a id="schemagenerateapicredentialbysignature"></a>
<a id="schema_GenerateApiCredentialBySignature"></a>
<a id="tocSgenerateapicredentialbysignature"></a>
<a id="tocsgenerateapicredentialbysignature"></a>

```json
{
  "apiKey": "string",
  "secret": "string",
  "passphrase": "string"
}

```

调用接口的接口认证凭据

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|apiKey|string|false|none||Api Key|
|secret|string|false|none||密钥 用来生成 hmac-sha256 签名|
|passphrase|string|false|none||密码，用于加解密secret|

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

<h2 id="tocS_Result<List<OrderFillTransaction>>">Result<List<OrderFillTransaction>></h2>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[OrderFillTransaction](#schemaorderfilltransaction)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Result<PageData<OrderFillTransaction>>">Result<PageData<OrderFillTransaction>></h2>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[PageDataOrderFillTransaction](#schemapagedataorderfilltransaction)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[OrderFillTransaction](#schemaorderfilltransaction)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

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

委托单成交明细

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||唯一标识|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|contractId|string(int64)|false|none||所属合约id|
|orderId|string(int64)|false|none||所属委托单id|
|orderSide|string|false|none||买卖方向|
|fillSize|string|false|none||实际成交数量|
|fillValue|string|false|none||实际成交价值|
|fillFee|string|false|none||实际成交费用|
|fillPrice|string|false|none||成交价格 (非精确值，仅展示使用)|
|liquidateFee|string|false|none||如果是清算(强平)成交，此字段为清算费用|
|realizePnl|string|false|none||实际已实现盈亏(成交包含平仓才会有值)|
|direction|string|false|none||实际成交方向|
|isPositionTpsl|boolean|false|none||是否为仓位止盈止损单|
|isLiquidate|boolean|false|none||是否是清算(强平)单成交|
|isDeleverage|boolean|false|none||是否是自动减仓单成交|
|isWithoutMatch|boolean|false|none||是否为不经过撮合直接成交的委托单|
|matchSequenceId|string(int64)|false|none||提交撮合处理后的顺序id|
|matchIndex|integer(int32)|false|none||提交撮合处理后多次成交的index|
|matchTime|string(int64)|false|none||提交撮合处理后的时间|
|matchAccountId|string(int64)|false|none||成交对手账户id|
|matchOrderId|string(int64)|false|none||成交对手委托单id|
|matchFillId|string|false|none||撮合引擎返回的成交id|
|positionTransactionId|string(int64)|false|none||关联的仓位明细id。|
|collateralTransactionId|string(int64)|false|none||关联的抵押品明细id。|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
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

<h2 id="tocS_Result<PageData<Order>>">Result<PageData<Order>></h2>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[PageDataOrder](#schemapagedataorder)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[Order](#schemaorder)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Result<List<Order>>">Result<List<Order>></h2>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[[Order](#schemaorder)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

永续合约委托单信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||委托单id。取值大于0|
|userId|string(int64)|false|none||所属用户id|
|accountId|string(int64)|false|none||所属账户id|
|coinId|string(int64)|false|none||所属抵押品币种id|
|contractId|string(int64)|false|none||所属合约id|
|side|string|false|none||买卖方向|
|price|string|false|none||委托价格(最差可接受的价格), 实际为decimal类型。|
|size|string|false|none||委托数量, 实际为decimal类型|
|clientOrderId|string|false|none||客户自定义id，用于幂等校验|
|type|string|false|none||委托单类型|
|timeInForce|string|false|none||委托单执行策略。type为 LIMIT/STOP_LIMIT/TAKE_PROFIT_LIMIT 时有意义。|
|reduceOnly|boolean|false|none||是否是只减仓委托|
|triggerPrice|string|false|none||触发价格。type为 STOP_LIMIT/STOP_MARKET/TAKE_PROFIT_LIMIT/TAKE_PROFIT_MARKET 时有意义。如果为0代表字段为空。实际为decimal类型|
|triggerPriceType|string|false|none||价格类型。最新市价[默认],标记价格。。type为 STOP_LIMIT/STOP_MARKET/TAKE_PROFIT_LIMIT/TAKE_PROFIT_MARKET 时有意义。|
|expireTime|string(int64)|false|none||过期时间。|
|sourceKey|string|false|none||来源key，uuid|
|isPositionTpsl|boolean|false|none||是否为仓位止盈止损单|
|isLiquidate|boolean|false|none||是否是强平单|
|isDeleverage|boolean|false|none||是否是自动减仓单|
|openTpslParentOrderId|string(int64)|false|none||开仓止盈单，止损单的开仓单orderId|
|isSetOpenTp|boolean|false|none||是否设置开仓止盈|
|openTp|[OpenTpSl](#schemaopentpsl)|false|none||开仓止盈止损参数|
|isSetOpenSl|boolean|false|none||是否设置开仓止损|
|openSl|[OpenTpSl](#schemaopentpsl)|false|none||开仓止盈止损参数|
|isWithoutMatch|boolean|false|none||是否为不经过撮合直接场外成交的委托单|
|withoutMatchFillSize|string|false|none||场外交易成交数量 (仅当 is_without_match 为 true 时有效)|
|withoutMatchFillValue|string|false|none||场外交易成交价值 (仅当 is_without_match 为 true 时有效)|
|withoutMatchPeerAccountId|string(int64)|false|none||场外交易对手accountId (仅当 is_without_match 为 true 时有效)|
|withoutMatchPeerOrderId|string(int64)|false|none||场外交易对手orderId (仅当 is_without_match 为 true 时有效)|
|maxLeverage|string|false|none||下单时开仓杠杆倍数, 实际为decimal类型|
|takerFeeRate|string|false|none||下单时taker手续费率, 实际为decimal类型|
|makerFeeRate|string|false|none||下单时maker手续费率, 实际为decimal类型|
|liquidateFeeRate|string|false|none||下单时清算手续费率, 实际为decimal类型|
|marketLimitPrice|string|false|none||市价单提交撮合的限价 (仅市价单存在,其他情况为0), 实际为decimal类型|
|marketLimitValue|string|false|none||市价单提交撮合的限定成交价值 (仅市价单存在,其他情况为0), 实际为decimal类型|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_order_id) 前32个bit|
|l2Value|string|false|none||l2签名委托价值(实际成交价必须等于或优于 l2_value / l2_size), 与 price x size 的值可能不一样。实际为decimal类型|
|l2Size|string|false|none||l2签名委托数量, 与size字段可能不一样。实际为decimal类型|
|l2LimitFee|string|false|none||l2签名最高可以接受的下单费用|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间，单位毫秒。参与签名生成/校验时要取小时数，即 l2_expire_time / 3600000。注意此字段必须要大于等于 expire_time + 8 * 24 * 60 * 60 * 1000(8天)|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|
|status|string|false|none||委托单状态|
|matchSequenceId|string(int64)|false|none||撮合引擎已处理序号id|
|triggerTime|string(int64)|false|none||条件单触发时间|
|triggerPriceTime|string(int64)|false|none||条件单触发价格时间|
|triggerPriceValue|string|false|none||条件单触发价格值|
|cancelReason|string|false|none||委托单取消原因|
|cumFillSize|string(decimal)|false|none||累计审查通过后的成交数量, 实际为decimal类型|
|cumFillValue|string(decimal)|false|none||累计审查通过后的成交价值, 实际为decimal类型|
|cumFillFee|string(decimal)|false|none||累计审查通过后的成交手续费, 实际为decimal类型|
|maxFillPrice|string(decimal)|false|none||当前委托单审查通过后的最高成交价格, 实际为decimal类型|
|minFillPrice|string(decimal)|false|none||当前委托单审查通过后的最低成交价格, 实际为decimal类型|
|cumLiquidateFee|string(decimal)|false|none||累计查通过后的强平清算费, 实际为decimal类型|
|cumRealizePnl|string(decimal)|false|none||累计查通过后的已实现盈亏, 实际为decimal类型|
|cumMatchSize|string(decimal)|false|none||累计撮合数量,实际为decimal类型|
|cumMatchValue|string(decimal)|false|none||累计撮合价值,实际为decimal类型|
|cumMatchFee|string(decimal)|false|none||累计撮合手续费，实际为decimal类型|
|cumFailSize|string|false|none||累计审查失败/L2拒绝的数量, 实际为decimal类型|
|cumFailValue|string|false|none||累计审查失败/L2拒绝的价值, 实际为decimal类型|
|cumFailFee|string|false|none||累计审查失败/L2拒绝的手续费, 实际为decimal类型|
|cumApprovedSize|string|false|none||累计L2确认的数量|
|cumApprovedValue|string|false|none||累计L2确认的价值|
|cumApprovedFee|string|false|none||累计L2确认的手续费|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

#### 枚举值

|属性|值|
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

开仓止盈止损参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|side|string|false|none||买卖方向,此字段必填|
|price|string|false|none||委托价格(最差可接受的价格), 实际为decimal类型。此字段必填，市价单时填0|
|size|string|false|none||委托数量, 实际为decimal类型。此字段必填|
|clientOrderId|string|false|none||客户自定义id，用于签名&幂等校验。此字段必填|
|triggerPrice|string|false|none||触发价格。此字段必填|
|triggerPriceType|string|false|none||价格类型。最新市价[默认],标记价格。此字段必填。|
|expireTime|string(int64)|false|none||过期时间。|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_order_id) 前32个bit|
|l2Value|string|false|none||l2签名委托价值(实际成交价必须等于或优于 l2_value / l2_price), 与 price x size 的值可能不一样。实际为decimal类型|
|l2Size|string|false|none||l2签名委托数量, 与size字段可能不一样。实际为decimal类型|
|l2LimitFee|string|false|none||l2签名最高可以接受的下单费用|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间. unix时间的小时数，至少要比 expire_time 晚10个小时|
|l2Signature|[L2Signature](#schemal2signature)|false|none||L2签名信息|

#### 枚举值

|属性|值|
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

<h2 id="tocS_Result<CheckUserNicknameExist>">Result<CheckUserNicknameExist></h2>

<a id="schemaresult<checkusernicknameexist>"></a>
<a id="schema_Result<CheckUserNicknameExist>"></a>
<a id="tocSresult<checkusernicknameexist>"></a>
<a id="tocsresult<checkusernicknameexist>"></a>

```json
{
  "code": "string",
  "data": {
    "isNicknameExist": true
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
|data|[CheckUserNicknameExist](#schemacheckusernicknameexist)|false|none||检测用户昵称是否存在-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CheckUserNicknameExist">CheckUserNicknameExist</h2>

<a id="schemacheckusernicknameexist"></a>
<a id="schema_CheckUserNicknameExist"></a>
<a id="tocScheckusernicknameexist"></a>
<a id="tocscheckusernicknameexist"></a>

```json
{
  "isNicknameExist": true
}

```

检测用户昵称是否存在-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|isNicknameExist|boolean|false|none||昵称是否存在|

<h2 id="tocS_Result<ClaimFaucetCoin>">Result<ClaimFaucetCoin></h2>

<a id="schemaresult<claimfaucetcoin>"></a>
<a id="schema_Result<ClaimFaucetCoin>"></a>
<a id="tocSresult<claimfaucetcoin>"></a>
<a id="tocsresult<claimfaucetcoin>"></a>

```json
{
  "code": "string",
  "data": {
    "isSuccess": true,
    "nextClaimTime": "string"
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
|data|[ClaimFaucetCoin](#schemaclaimfaucetcoin)|false|none||领取水龙头体验代币-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_ClaimFaucetCoin">ClaimFaucetCoin</h2>

<a id="schemaclaimfaucetcoin"></a>
<a id="schema_ClaimFaucetCoin"></a>
<a id="tocSclaimfaucetcoin"></a>
<a id="tocsclaimfaucetcoin"></a>

```json
{
  "isSuccess": true,
  "nextClaimTime": "string"
}

```

领取水龙头体验代币-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|isSuccess|boolean|false|none||是否领取成功|
|nextClaimTime|string|false|none||下次可领取时间|

<h2 id="tocS_Result<PageData<FaucetCoinClaim>>">Result<PageData<FaucetCoinClaim>></h2>

<a id="schemaresult<pagedata<faucetcoinclaim>>"></a>
<a id="schema_Result<PageData<FaucetCoinClaim>>"></a>
<a id="tocSresult<pagedata<faucetcoinclaim>>"></a>
<a id="tocsresult<pagedata<faucetcoinclaim>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "ethAddress": "string",
        "faucetAddress": "string",
        "status": "UNKNOWN_FAUCET_COIN_CLAIM_STATUS",
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
|data|[PageDataFaucetCoinClaim](#schemapagedatafaucetcoinclaim)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataFaucetCoinClaim">PageDataFaucetCoinClaim</h2>

<a id="schemapagedatafaucetcoinclaim"></a>
<a id="schema_PageDataFaucetCoinClaim"></a>
<a id="tocSpagedatafaucetcoinclaim"></a>
<a id="tocspagedatafaucetcoinclaim"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "ethAddress": "string",
      "faucetAddress": "string",
      "status": "UNKNOWN_FAUCET_COIN_CLAIM_STATUS",
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
|dataList|[[FaucetCoinClaim](#schemafaucetcoinclaim)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_FaucetCoinClaim">FaucetCoinClaim</h2>

<a id="schemafaucetcoinclaim"></a>
<a id="schema_FaucetCoinClaim"></a>
<a id="tocSfaucetcoinclaim"></a>
<a id="tocsfaucetcoinclaim"></a>

```json
{
  "id": "string",
  "userId": "string",
  "ethAddress": "string",
  "faucetAddress": "string",
  "status": "UNKNOWN_FAUCET_COIN_CLAIM_STATUS",
  "createdTime": "string",
  "updatedTime": "string"
}

```

水龙头领取记录

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||领取记录id|
|userId|string(int64)|false|none||领取用户id|
|ethAddress|string|false|none||领取用户eth地址|
|faucetAddress|string|false|none||水龙头发放地址|
|status|string|false|none||领取状态|
|createdTime|string|false|none||领取时间|
|updatedTime|string|false|none||更新时间|

#### 枚举值

|属性|值|
|---|---|
|status|UNKNOWN_FAUCET_COIN_CLAIM_STATUS|
|status|PENDING|
|status|PROCESSING|
|status|SUCCESS|
|status|FAILED|
|status|UNRECOGNIZED|

<h2 id="tocS_SiteMessage">SiteMessage</h2>

<a id="schemasitemessage"></a>
<a id="schema_SiteMessage"></a>
<a id="tocSsitemessage"></a>
<a id="tocssitemessage"></a>

```json
{
  "id": "string",
  "userId": "string",
  "businessType": "string",
  "notifyCategory": 0,
  "title": "string",
  "content": "string",
  "webJumpUrl": "string",
  "androidJumpUrl": "string",
  "iosJumpUrl": "string",
  "isRead": true,
  "createdTime": "string",
  "updatedTime": "string"
}

```

站内信详情

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||站内信Id|
|userId|string|false|none||用户Id|
|businessType|string|false|none||站内信消息业务类型(小类)|
|notifyCategory|integer(int32)|false|none||站内信消息类型(大类)|
|title|string|false|none||站内信标题|
|content|string|false|none||站内信内容|
|webJumpUrl|string|false|none||Web跳转链接|
|androidJumpUrl|string|false|none||Android跳转链接|
|iosJumpUrl|string|false|none||iOS跳转链接|
|isRead|boolean|false|none||是否已读|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

<h2 id="tocS_Result<PageData<SiteMessage>>">Result<PageData<SiteMessage>></h2>

<a id="schemaresult<pagedata<sitemessage>>"></a>
<a id="schema_Result<PageData<SiteMessage>>"></a>
<a id="tocSresult<pagedata<sitemessage>>"></a>
<a id="tocsresult<pagedata<sitemessage>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "id": "string",
        "userId": "string",
        "businessType": "string",
        "notifyCategory": 0,
        "title": "string",
        "content": "string",
        "webJumpUrl": "string",
        "androidJumpUrl": "string",
        "iosJumpUrl": "string",
        "isRead": true,
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
|data|[PageDataSiteMessage](#schemapagedatasitemessage)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataSiteMessage">PageDataSiteMessage</h2>

<a id="schemapagedatasitemessage"></a>
<a id="schema_PageDataSiteMessage"></a>
<a id="tocSpagedatasitemessage"></a>
<a id="tocspagedatasitemessage"></a>

```json
{
  "dataList": [
    {
      "id": "string",
      "userId": "string",
      "businessType": "string",
      "notifyCategory": 0,
      "title": "string",
      "content": "string",
      "webJumpUrl": "string",
      "androidJumpUrl": "string",
      "iosJumpUrl": "string",
      "isRead": true,
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
|dataList|[[SiteMessage](#schemasitemessage)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_UserInfo">UserInfo</h2>

<a id="schemauserinfo"></a>
<a id="schema_UserInfo"></a>
<a id="tocSuserinfo"></a>
<a id="tocsuserinfo"></a>

```json
{
  "user": {
    "id": "string",
    "ethAddress": "string",
    "nickname": "string",
    "email": "string",
    "isEmailVerified": true,
    "country": "string",
    "language": "string",
    "avatarUrl": "string",
    "avatarBorderUrl": "string",
    "createdTime": "string",
    "updatedTime": "string"
  },
  "userPreference": {
    "userId": "string",
    "isSharingEthAddress": true,
    "isSharingNickname": true,
    "isEmailNotifyGeneralEnable": true,
    "isEmailNotifyTradingEnable": true,
    "isEmailNotifyAccountEnable": true,
    "isAppNotifyTradingEnable": true,
    "createdTime": "string",
    "updatedTime": "string"
  }
}

```

用户信息和用户设置信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|user|[User](#schemauser)|false|none||用户信息|
|userPreference|[UserPreference](#schemauserpreference)|false|none||用户设置|

<h2 id="tocS_Result<UserInfo>">Result<UserInfo></h2>

<a id="schemaresult<userinfo>"></a>
<a id="schema_Result<UserInfo>"></a>
<a id="tocSresult<userinfo>"></a>
<a id="tocsresult<userinfo>"></a>

```json
{
  "code": "string",
  "data": {
    "user": {
      "id": "string",
      "ethAddress": "string",
      "nickname": "string",
      "email": "string",
      "isEmailVerified": true,
      "country": "string",
      "language": "string",
      "avatarUrl": "string",
      "avatarBorderUrl": "string",
      "createdTime": "string",
      "updatedTime": "string"
    },
    "userPreference": {
      "userId": "string",
      "isSharingEthAddress": true,
      "isSharingNickname": true,
      "isEmailNotifyGeneralEnable": true,
      "isEmailNotifyTradingEnable": true,
      "isEmailNotifyAccountEnable": true,
      "isAppNotifyTradingEnable": true,
      "createdTime": "string",
      "updatedTime": "string"
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
|data|[UserInfo](#schemauserinfo)|false|none||用户信息和用户设置信息|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Result<UserPreference>">Result<UserPreference></h2>

<a id="schemaresult<userpreference>"></a>
<a id="schema_Result<UserPreference>"></a>
<a id="tocSresult<userpreference>"></a>
<a id="tocsresult<userpreference>"></a>

```json
{
  "code": "string",
  "data": {
    "userId": "string",
    "isSharingEthAddress": true,
    "isSharingNickname": true,
    "isEmailNotifyGeneralEnable": true,
    "isEmailNotifyTradingEnable": true,
    "isEmailNotifyAccountEnable": true,
    "isAppNotifyTradingEnable": true,
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
|data|[UserPreference](#schemauserpreference)|false|none||用户设置|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Result<User>">Result<User></h2>

<a id="schemaresult<user>"></a>
<a id="schema_Result<User>"></a>
<a id="tocSresult<user>"></a>
<a id="tocsresult<user>"></a>

```json
{
  "code": "string",
  "data": {
    "id": "string",
    "ethAddress": "string",
    "nickname": "string",
    "email": "string",
    "isEmailVerified": true,
    "country": "string",
    "language": "string",
    "avatarUrl": "string",
    "avatarBorderUrl": "string",
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
|data|[User](#schemauser)|false|none||用户信息|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

<h2 id="tocS_TxInfo">TxInfo</h2>

<a id="schematxinfo"></a>
<a id="schema_TxInfo"></a>
<a id="tocStxinfo"></a>
<a id="tocstxinfo"></a>

```json
{
  "from": "string",
  "to": "string",
  "data": "string",
  "value": "string",
  "gas": "string",
  "gasPrice": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|from|string|false|none||none|
|to|string|false|none||none|
|data|string|false|none||none|
|value|string|false|none||none|
|gas|string|false|none||none|
|gasPrice|string|false|none||none|

<h2 id="tocS_Result<GetAggregateExchangeData>">Result<GetAggregateExchangeData></h2>

<a id="schemaresult<getaggregateexchangedata>"></a>
<a id="schema_Result<GetAggregateExchangeData>"></a>
<a id="tocSresult<getaggregateexchangedata>"></a>
<a id="tocsresult<getaggregateexchangedata>"></a>

```json
{
  "code": "string",
  "data": {
    "toAmount": "string",
    "tx": {
      "from": "string",
      "to": "string",
      "data": "string",
      "value": "string",
      "gas": "string",
      "gasPrice": "string"
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
|data|[GetAggregateExchangeData](#schemagetaggregateexchangedata)|false|none||获取聚合exchange data-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetAggregateExchangeData">GetAggregateExchangeData</h2>

<a id="schemagetaggregateexchangedata"></a>
<a id="schema_GetAggregateExchangeData"></a>
<a id="tocSgetaggregateexchangedata"></a>
<a id="tocsgetaggregateexchangedata"></a>

```json
{
  "toAmount": "string",
  "tx": {
    "from": "string",
    "to": "string",
    "data": "string",
    "value": "string",
    "gas": "string",
    "gasPrice": "string"
  }
}

```

获取聚合exchange data-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|toAmount|string|false|none||none|
|tx|[TxInfo](#schematxinfo)|false|none||none|

<h2 id="tocS_Result<Get1inchQuote>">Result<Get1inchQuote></h2>

<a id="schemaresult<get1inchquote>"></a>
<a id="schema_Result<Get1inchQuote>"></a>
<a id="tocSresult<get1inchquote>"></a>
<a id="tocsresult<get1inchquote>"></a>

```json
{
  "code": "string",
  "data": {
    "toAmount": "string",
    "gas": "string"
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
|data|[Get1inchQuote](#schemaget1inchquote)|false|none||获取1inch币对兑换汇率-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Get1inchQuote">Get1inchQuote</h2>

<a id="schemaget1inchquote"></a>
<a id="schema_Get1inchQuote"></a>
<a id="tocSget1inchquote"></a>
<a id="tocsget1inchquote"></a>

```json
{
  "toAmount": "string",
  "gas": "string"
}

```

获取1inch币对兑换汇率-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|toAmount|string|false|none||返回的汇率，带精度|
|gas|string|false|none||gas|

<h2 id="tocS_Result<AppUpdate>">Result<AppUpdate></h2>

<a id="schemaresult<appupdate>"></a>
<a id="schema_Result<AppUpdate>"></a>
<a id="tocSresult<appupdate>"></a>
<a id="tocsresult<appupdate>"></a>

```json
{
  "code": "string",
  "data": {
    "latestVersion": "string",
    "downloadUrl": "string",
    "marketUrl": "string",
    "description": "string",
    "beForceUpdate": true,
    "beUpdate": true
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
|data|[AppUpdate](#schemaappupdate)|false|none||APP升级信息|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_AppUpdate">AppUpdate</h2>

<a id="schemaappupdate"></a>
<a id="schema_AppUpdate"></a>
<a id="tocSappupdate"></a>
<a id="tocsappupdate"></a>

```json
{
  "latestVersion": "string",
  "downloadUrl": "string",
  "marketUrl": "string",
  "description": "string",
  "beForceUpdate": true,
  "beUpdate": true
}

```

APP升级信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|latestVersion|string|false|none||none|
|downloadUrl|string|false|none||none|
|marketUrl|string|false|none||none|
|description|string|false|none||none|
|beForceUpdate|boolean|false|none||none|
|beUpdate|boolean|false|none||none|

<h2 id="tocS_Result<PageData<FundingRate>>">Result<PageData<FundingRate>></h2>

<a id="schemaresult<pagedata<fundingrate>>"></a>
<a id="schema_Result<PageData<FundingRate>>"></a>
<a id="tocSresult<pagedata<fundingrate>>"></a>
<a id="tocsresult<pagedata<fundingrate>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "contractId": "string",
        "fundingTime": "string",
        "fundingTimestamp": "string",
        "oraclePrice": "string",
        "indexPrice": "string",
        "fundingRate": "string",
        "isSettlement": true,
        "forecastFundingRate": "string",
        "previousFundingRate": "string",
        "previousFundingTimestamp": "string",
        "premiumIndex": "string",
        "avgPremiumIndex": "string",
        "premiumIndexTimestamp": "string",
        "impactMarginNotional": "string",
        "impactAskPrice": "string",
        "impactBidPrice": "string",
        "interestRate": "string",
        "predictedFundingRate": "string",
        "fundingRateIntervalMin": "string",
        "starkExFundingIndex": "string"
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
|data|[PageDataFundingRate](#schemapagedatafundingrate)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataFundingRate">PageDataFundingRate</h2>

<a id="schemapagedatafundingrate"></a>
<a id="schema_PageDataFundingRate"></a>
<a id="tocSpagedatafundingrate"></a>
<a id="tocspagedatafundingrate"></a>

```json
{
  "dataList": [
    {
      "contractId": "string",
      "fundingTime": "string",
      "fundingTimestamp": "string",
      "oraclePrice": "string",
      "indexPrice": "string",
      "fundingRate": "string",
      "isSettlement": true,
      "forecastFundingRate": "string",
      "previousFundingRate": "string",
      "previousFundingTimestamp": "string",
      "premiumIndex": "string",
      "avgPremiumIndex": "string",
      "premiumIndexTimestamp": "string",
      "impactMarginNotional": "string",
      "impactAskPrice": "string",
      "impactBidPrice": "string",
      "interestRate": "string",
      "predictedFundingRate": "string",
      "fundingRateIntervalMin": "string",
      "starkExFundingIndex": "string"
    }
  ],
  "nextPageOffsetData": "string"
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[FundingRate](#schemafundingrate)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Result<List<FundingRate>>">Result<List<FundingRate>></h2>

<a id="schemaresult<list<fundingrate>>"></a>
<a id="schema_Result<List<FundingRate>>"></a>
<a id="tocSresult<list<fundingrate>>"></a>
<a id="tocsresult<list<fundingrate>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "fundingTime": "string",
      "fundingTimestamp": "string",
      "oraclePrice": "string",
      "indexPrice": "string",
      "fundingRate": "string",
      "isSettlement": true,
      "forecastFundingRate": "string",
      "previousFundingRate": "string",
      "previousFundingTimestamp": "string",
      "premiumIndex": "string",
      "avgPremiumIndex": "string",
      "premiumIndexTimestamp": "string",
      "impactMarginNotional": "string",
      "impactAskPrice": "string",
      "impactBidPrice": "string",
      "interestRate": "string",
      "predictedFundingRate": "string",
      "fundingRateIntervalMin": "string",
      "starkExFundingIndex": "string"
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
|data|[[FundingRate](#schemafundingrate)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_FundingRate">FundingRate</h2>

<a id="schemafundingrate"></a>
<a id="schema_FundingRate"></a>
<a id="tocSfundingrate"></a>
<a id="tocsfundingrate"></a>

```json
{
  "contractId": "string",
  "fundingTime": "string",
  "fundingTimestamp": "string",
  "oraclePrice": "string",
  "indexPrice": "string",
  "fundingRate": "string",
  "isSettlement": true,
  "forecastFundingRate": "string",
  "previousFundingRate": "string",
  "previousFundingTimestamp": "string",
  "premiumIndex": "string",
  "avgPremiumIndex": "string",
  "premiumIndexTimestamp": "string",
  "impactMarginNotional": "string",
  "impactAskPrice": "string",
  "impactBidPrice": "string",
  "interestRate": "string",
  "predictedFundingRate": "string",
  "fundingRateIntervalMin": "string",
  "starkExFundingIndex": "string"
}

```

资金费率

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约ID|
|fundingTime|string(int64)|false|none||资金费率结算时间 如08:00-09:00这一期的资金费率，是通过上一期07:00-08:00的数据计算而得，在08:00的时候已经确定，在09:00进行结算时使用|
|fundingTimestamp|string(int64)|false|none||费率计算时间 millisecond|
|oraclePrice|string|false|none||预言机价格|
|indexPrice|string|false|none||指数价格|
|fundingRate|string|false|none||资金费率|
|isSettlement|boolean|false|none||资金费率结算标志|
|forecastFundingRate|string|false|none||预测资金费率|
|previousFundingRate|string|false|none||上一次的资金费率|
|previousFundingTimestamp|string(int64)|false|none||上一次资金费率计算时间 millisecond|
|premiumIndex|string|false|none||溢价指数|
|avgPremiumIndex|string|false|none||平均溢价指数|
|premiumIndexTimestamp|string|false|none||溢价指数计算时间|
|impactMarginNotional|string|false|none||深度加权买卖价格需计算的数量|
|impactAskPrice|string|false|none||深度加权卖价|
|impactBidPrice|string|false|none||深度加权买价|
|interestRate|string|false|none||固定利率|
|predictedFundingRate|string|false|none||综合利率 interestRate/频率|
|fundingRateIntervalMin|string(int64)|false|none||资金费率时间间隔 min|
|starkExFundingIndex|string|false|none||资金费指数|

<h2 id="tocS_Result<List<IndexPriceConfig>>">Result<List<IndexPriceConfig>></h2>

<a id="schemaresult<list<indexpriceconfig>>"></a>
<a id="schema_Result<List<IndexPriceConfig>>"></a>
<a id="tocSresult<list<indexpriceconfig>>"></a>
<a id="tocsresult<list<indexpriceconfig>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "indexPriceExchangeInfoList": [
        {
          "exchangeName": "string",
          "exchangeQuote": "string",
          "weight": "string"
        }
      ]
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
|data|[[IndexPriceConfig](#schemaindexpriceconfig)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_IndexPriceExchangeInfo">IndexPriceExchangeInfo</h2>

<a id="schemaindexpriceexchangeinfo"></a>
<a id="schema_IndexPriceExchangeInfo"></a>
<a id="tocSindexpriceexchangeinfo"></a>
<a id="tocsindexpriceexchangeinfo"></a>

```json
{
  "exchangeName": "string",
  "exchangeQuote": "string",
  "weight": "string"
}

```

指数价格配置信息（交易所）

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|exchangeName|string|false|none||交易所|
|exchangeQuote|string|false|none||交易所币对|
|weight|string|false|none||权重|

<h2 id="tocS_IndexPriceConfig">IndexPriceConfig</h2>

<a id="schemaindexpriceconfig"></a>
<a id="schema_IndexPriceConfig"></a>
<a id="tocSindexpriceconfig"></a>
<a id="tocsindexpriceconfig"></a>

```json
{
  "contractId": "string",
  "indexPriceExchangeInfoList": [
    {
      "exchangeName": "string",
      "exchangeQuote": "string",
      "weight": "string"
    }
  ]
}

```

指数价格配置信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约id|
|indexPriceExchangeInfoList|[[IndexPriceExchangeInfo](#schemaindexpriceexchangeinfo)]|false|none||指数价格配置项|

<h2 id="tocS_RiskTier">RiskTier</h2>

<a id="schemarisktier"></a>
<a id="schema_RiskTier"></a>
<a id="tocSrisktier"></a>
<a id="tocsrisktier"></a>

```json
{
  "tier": 0,
  "positionValueUpperBound": "string",
  "maxLeverage": "string",
  "maintenanceMarginRate": "string",
  "starkExRisk": "string",
  "starkExUpperBound": "string"
}

```

风险限额档位信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|tier|integer(int32)|false|none||档位，从1开始|
|positionValueUpperBound|string(decimal)|false|none||档位仓位价值上限 (包含)|
|maxLeverage|string(decimal)|false|none||档位最高可用杠杆|
|maintenanceMarginRate|string(decimal)|false|none||档位维持保证金率 (仅用于展示，实际使用 stark_ex_risk / 2^32 做为精确维持保证金率)，decimal|
|starkExRisk|string(int64)|false|none||1 ≤ risk < 2^32|
|starkExUpperBound|string(int64)|false|none||bigint. 0 ≤ upper_bound ≤ 2^128-1|

<h2 id="tocS_Result<MetaData>">Result<MetaData></h2>

<a id="schemaresult<metadata>"></a>
<a id="schema_Result<MetaData>"></a>
<a id="tocSresult<metadata>"></a>
<a id="tocsresult<metadata>"></a>

```json
{
  "code": "string",
  "data": {
    "global": {
      "appName": "string",
      "appEnv": "string",
      "appOnlySignOn": "string",
      "feeAccountId": "string",
      "feeAccountL2Key": "string",
      "poolAccountId": "string",
      "poolAccountL2Key": "string",
      "fastWithdrawAccountId": "string",
      "fastWithdrawAccountL2Key": "string",
      "fastWithdrawMaxAmount": "string",
      "fastWithdrawRegistryAddress": "string",
      "starkExChainId": "string",
      "starkExContractAddress": "string",
      "starkExCollateralCoin": {
        "coinId": "string",
        "coinName": "string",
        "stepSize": "string",
        "showStepSize": "string",
        "iconUrl": "string",
        "starkExAssetId": "string",
        "starkExResolution": "string"
      },
      "starkExMaxFundingRate": 0,
      "starkExOrdersTreeHeight": 0,
      "starkExPositionsTreeHeight": 0,
      "starkExFundingValidityPeriod": 0,
      "starkExPriceValidityPeriod": 0,
      "maintenanceReason": "string"
    },
    "coinList": [
      {
        "coinId": "string",
        "coinName": "string",
        "stepSize": "string",
        "showStepSize": "string",
        "iconUrl": "string",
        "starkExAssetId": "string",
        "starkExResolution": "string"
      }
    ],
    "contractList": [
      {
        "contractId": "string",
        "contractName": "string",
        "baseCoinId": "string",
        "quoteCoinId": "string",
        "tickSize": "string",
        "stepSize": "string",
        "minOrderSize": "string",
        "maxOrderSize": "string",
        "maxOrderBuyPriceRatio": "string",
        "minOrderSellPriceRatio": "string",
        "maxPositionSize": "string",
        "riskTierList": [
          {
            "tier": null,
            "positionValueUpperBound": null,
            "maxLeverage": null,
            "maintenanceMarginRate": null,
            "starkExRisk": null,
            "starkExUpperBound": null
          }
        ],
        "defaultTakerFeeRate": "string",
        "defaultMakerFeeRate": "string",
        "defaultLeverage": "string",
        "liquidateFeeRate": "string",
        "enableTrade": true,
        "enableDisplay": true,
        "enableOpenPosition": true,
        "fundingInterestRate": "string",
        "fundingImpactMarginNotional": "string",
        "fundingMaxRate": "string",
        "fundingMinRate": "string",
        "fundingRateIntervalMin": "string",
        "displayDigitMerge": "string",
        "displayMaxLeverage": "string",
        "displayMinLeverage": "string",
        "displayNewIcon": true,
        "displayHotIcon": true,
        "matchServerName": "string",
        "starkExSyntheticAssetId": "string",
        "starkExResolution": "string",
        "starkExOraclePriceQuorum": "string",
        "starkExOraclePriceSignedAssetId": [
          "string"
        ],
        "starkExOraclePriceSigner": [
          "string"
        ]
      }
    ],
    "multiChain": {
      "coinId": "string",
      "maxWithdraw": "string",
      "minWithdraw": "string",
      "minDeposit": "string",
      "chainList": [
        {
          "chain": "string",
          "chainId": "string",
          "chainIconUrl": "string",
          "contractAddress": "string",
          "depositGasFeeLess": true,
          "feeLess": true,
          "feeRate": "string",
          "gasLess": true,
          "gasToken": "string",
          "minFee": "string",
          "rpcUrl": "string",
          "webTxUrl": "string",
          "withdrawGasFeeLess": true,
          "tokenList": [
            null
          ],
          "txConfirm": "string",
          "blockTime": "string",
          "appRpcUrl": "string"
        }
      ]
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
|data|[MetaData](#schemametadata)|false|none||全局元数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_MultiChainToken">MultiChainToken</h2>

<a id="schemamultichaintoken"></a>
<a id="schema_MultiChainToken"></a>
<a id="tocSmultichaintoken"></a>
<a id="tocsmultichaintoken"></a>

```json
{
  "tokenAddress": "string",
  "decimals": "string",
  "iconUrl": "string",
  "token": "string",
  "pullOff": true,
  "withdrawEnable": true,
  "useFixedRate": true,
  "fixedRate": "string"
}

```

跨链相关币种类

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|tokenAddress|string|false|none||token合约地址|
|decimals|string(int64)|false|none||token精度|
|iconUrl|string|false|none||token图标url|
|token|string|false|none||token name|
|pullOff|boolean|false|none||是否下架，默认false|
|withdrawEnable|boolean|false|none||是否支持提现该类型资产|
|useFixedRate|boolean|false|none||是否使用固定汇率|
|fixedRate|string|false|none||固定汇率|

<h2 id="tocS_MultiChain">MultiChain</h2>

<a id="schemamultichain"></a>
<a id="schema_MultiChain"></a>
<a id="tocSmultichain"></a>
<a id="tocsmultichain"></a>

```json
{
  "coinId": "string",
  "maxWithdraw": "string",
  "minWithdraw": "string",
  "minDeposit": "string",
  "chainList": [
    {
      "chain": "string",
      "chainId": "string",
      "chainIconUrl": "string",
      "contractAddress": "string",
      "depositGasFeeLess": true,
      "feeLess": true,
      "feeRate": "string",
      "gasLess": true,
      "gasToken": "string",
      "minFee": "string",
      "rpcUrl": "string",
      "webTxUrl": "string",
      "withdrawGasFeeLess": true,
      "tokenList": [
        {
          "tokenAddress": "string",
          "decimals": "string",
          "iconUrl": "string",
          "token": "string",
          "pullOff": true,
          "withdrawEnable": true,
          "useFixedRate": true,
          "fixedRate": "string"
        }
      ],
      "txConfirm": "string",
      "blockTime": "string",
      "appRpcUrl": "string"
    }
  ]
}

```

跨链提币相关类

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|coinId|string(int64)|false|none||充提资产id|
|maxWithdraw|string|false|none||最大提币量|
|minWithdraw|string|false|none||最小提币量|
|minDeposit|string|false|none||最小充币量|
|chainList|[[Chain](#schemachain)]|false|none||支持的链|

<h2 id="tocS_MetaData">MetaData</h2>

<a id="schemametadata"></a>
<a id="schema_MetaData"></a>
<a id="tocSmetadata"></a>
<a id="tocsmetadata"></a>

```json
{
  "global": {
    "appName": "string",
    "appEnv": "string",
    "appOnlySignOn": "string",
    "feeAccountId": "string",
    "feeAccountL2Key": "string",
    "poolAccountId": "string",
    "poolAccountL2Key": "string",
    "fastWithdrawAccountId": "string",
    "fastWithdrawAccountL2Key": "string",
    "fastWithdrawMaxAmount": "string",
    "fastWithdrawRegistryAddress": "string",
    "starkExChainId": "string",
    "starkExContractAddress": "string",
    "starkExCollateralCoin": {
      "coinId": "string",
      "coinName": "string",
      "stepSize": "string",
      "showStepSize": "string",
      "iconUrl": "string",
      "starkExAssetId": "string",
      "starkExResolution": "string"
    },
    "starkExMaxFundingRate": 0,
    "starkExOrdersTreeHeight": 0,
    "starkExPositionsTreeHeight": 0,
    "starkExFundingValidityPeriod": 0,
    "starkExPriceValidityPeriod": 0,
    "maintenanceReason": "string"
  },
  "coinList": [
    {
      "coinId": "string",
      "coinName": "string",
      "stepSize": "string",
      "showStepSize": "string",
      "iconUrl": "string",
      "starkExAssetId": "string",
      "starkExResolution": "string"
    }
  ],
  "contractList": [
    {
      "contractId": "string",
      "contractName": "string",
      "baseCoinId": "string",
      "quoteCoinId": "string",
      "tickSize": "string",
      "stepSize": "string",
      "minOrderSize": "string",
      "maxOrderSize": "string",
      "maxOrderBuyPriceRatio": "string",
      "minOrderSellPriceRatio": "string",
      "maxPositionSize": "string",
      "riskTierList": [
        {
          "tier": 0,
          "positionValueUpperBound": "string",
          "maxLeverage": "string",
          "maintenanceMarginRate": "string",
          "starkExRisk": "string",
          "starkExUpperBound": "string"
        }
      ],
      "defaultTakerFeeRate": "string",
      "defaultMakerFeeRate": "string",
      "defaultLeverage": "string",
      "liquidateFeeRate": "string",
      "enableTrade": true,
      "enableDisplay": true,
      "enableOpenPosition": true,
      "fundingInterestRate": "string",
      "fundingImpactMarginNotional": "string",
      "fundingMaxRate": "string",
      "fundingMinRate": "string",
      "fundingRateIntervalMin": "string",
      "displayDigitMerge": "string",
      "displayMaxLeverage": "string",
      "displayMinLeverage": "string",
      "displayNewIcon": true,
      "displayHotIcon": true,
      "matchServerName": "string",
      "starkExSyntheticAssetId": "string",
      "starkExResolution": "string",
      "starkExOraclePriceQuorum": "string",
      "starkExOraclePriceSignedAssetId": [
        "string"
      ],
      "starkExOraclePriceSigner": [
        "string"
      ]
    }
  ],
  "multiChain": {
    "coinId": "string",
    "maxWithdraw": "string",
    "minWithdraw": "string",
    "minDeposit": "string",
    "chainList": [
      {
        "chain": "string",
        "chainId": "string",
        "chainIconUrl": "string",
        "contractAddress": "string",
        "depositGasFeeLess": true,
        "feeLess": true,
        "feeRate": "string",
        "gasLess": true,
        "gasToken": "string",
        "minFee": "string",
        "rpcUrl": "string",
        "webTxUrl": "string",
        "withdrawGasFeeLess": true,
        "tokenList": [
          {
            "tokenAddress": null,
            "decimals": null,
            "iconUrl": null,
            "token": null,
            "pullOff": null,
            "withdrawEnable": null,
            "useFixedRate": null,
            "fixedRate": null
          }
        ],
        "txConfirm": "string",
        "blockTime": "string",
        "appRpcUrl": "string"
      }
    ]
  }
}

```

全局元数据

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|global|[Global](#schemaglobal)|false|none||全局元信息|
|coinList|[[Coin](#schemacoin)]|false|none||所有货币元信息|
|contractList|[[Contract](#schemacontract)]|false|none||所有合约元信息|
|multiChain|[MultiChain](#schemamultichain)|false|none||跨链提币相关类|

<h2 id="tocS_Global">Global</h2>

<a id="schemaglobal"></a>
<a id="schema_Global"></a>
<a id="tocSglobal"></a>
<a id="tocsglobal"></a>

```json
{
  "appName": "string",
  "appEnv": "string",
  "appOnlySignOn": "string",
  "feeAccountId": "string",
  "feeAccountL2Key": "string",
  "poolAccountId": "string",
  "poolAccountL2Key": "string",
  "fastWithdrawAccountId": "string",
  "fastWithdrawAccountL2Key": "string",
  "fastWithdrawMaxAmount": "string",
  "fastWithdrawRegistryAddress": "string",
  "starkExChainId": "string",
  "starkExContractAddress": "string",
  "starkExCollateralCoin": {
    "coinId": "string",
    "coinName": "string",
    "stepSize": "string",
    "showStepSize": "string",
    "iconUrl": "string",
    "starkExAssetId": "string",
    "starkExResolution": "string"
  },
  "starkExMaxFundingRate": 0,
  "starkExOrdersTreeHeight": 0,
  "starkExPositionsTreeHeight": 0,
  "starkExFundingValidityPeriod": 0,
  "starkExPriceValidityPeriod": 0,
  "maintenanceReason": "string"
}

```

全局元信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|appName|string|false|none||xxx|
|appEnv|string|false|none||dev/testnet/mainnet|
|appOnlySignOn|string|false|none||https://xxx.exchange|
|feeAccountId|string(int64)|false|none||手续费账户id|
|feeAccountL2Key|string|false|none||手续费账户l2Key，bigint for hex str|
|poolAccountId|string(int64)|false|none||资产池账户id|
|poolAccountL2Key|string|false|none||资产池账户l2Key，bigint for hex str|
|fastWithdrawAccountId|string(int64)|false|none||快速提币账户id|
|fastWithdrawAccountL2Key|string|false|none||快速提币账户l2Key，bigint for hex str|
|fastWithdrawMaxAmount|string|false|none||快速提币最大金额|
|fastWithdrawRegistryAddress|string|false|none||快速提币账户地址|
|starkExChainId|string|false|none||starkex 所属的 chain id. bigint for hex str|
|starkExContractAddress|string|false|none||starkex合约地址。|
|starkExCollateralCoin|[Coin](#schemacoin)|false|none||货币元信息|
|starkExMaxFundingRate|integer(int32)|false|none||starkex精度处理后的每秒最大资金费率。即 stark_ex_max_funding_rate * 2^32 为实际的每秒最大资金费率。例：1120|
|starkExOrdersTreeHeight|integer(int32)|false|none||订单merkle树高度。例：64|
|starkExPositionsTreeHeight|integer(int32)|false|none||账户merkle树高度。例：64|
|starkExFundingValidityPeriod|integer(int32)|false|none||资金费率提交有效期秒数。例：86400|
|starkExPriceValidityPeriod|integer(int32)|false|none||预言机价格提交有效期秒数。例：86400|
|maintenanceReason|string|false|none||维护原因，如果没维护就为空|

<h2 id="tocS_Contract">Contract</h2>

<a id="schemacontract"></a>
<a id="schema_Contract"></a>
<a id="tocScontract"></a>
<a id="tocscontract"></a>

```json
{
  "contractId": "string",
  "contractName": "string",
  "baseCoinId": "string",
  "quoteCoinId": "string",
  "tickSize": "string",
  "stepSize": "string",
  "minOrderSize": "string",
  "maxOrderSize": "string",
  "maxOrderBuyPriceRatio": "string",
  "minOrderSellPriceRatio": "string",
  "maxPositionSize": "string",
  "riskTierList": [
    {
      "tier": 0,
      "positionValueUpperBound": "string",
      "maxLeverage": "string",
      "maintenanceMarginRate": "string",
      "starkExRisk": "string",
      "starkExUpperBound": "string"
    }
  ],
  "defaultTakerFeeRate": "string",
  "defaultMakerFeeRate": "string",
  "defaultLeverage": "string",
  "liquidateFeeRate": "string",
  "enableTrade": true,
  "enableDisplay": true,
  "enableOpenPosition": true,
  "fundingInterestRate": "string",
  "fundingImpactMarginNotional": "string",
  "fundingMaxRate": "string",
  "fundingMinRate": "string",
  "fundingRateIntervalMin": "string",
  "displayDigitMerge": "string",
  "displayMaxLeverage": "string",
  "displayMinLeverage": "string",
  "displayNewIcon": true,
  "displayHotIcon": true,
  "matchServerName": "string",
  "starkExSyntheticAssetId": "string",
  "starkExResolution": "string",
  "starkExOraclePriceQuorum": "string",
  "starkExOraclePriceSignedAssetId": [
    "string"
  ],
  "starkExOraclePriceSigner": [
    "string"
  ]
}

```

永续合约元信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||永续合约币对标识|
|contractName|string|false|none||永续合约币对名称|
|baseCoinId|string(int64)|false|none||例如：10000001 (BTC)|
|quoteCoinId|string(int64)|false|none||例如：1001 (USD/USDT)|
|tickSize|string(decimal)|false|none||最小报价单位(quoteCoinId)|
|stepSize|string(decimal)|false|none||最小数量单位(baseCoinId)|
|minOrderSize|string(decimal)|false|none||最小委托单数量(baseCoinId)|
|maxOrderSize|string(decimal)|false|none||最大委托单数据(baseCoinId)|
|maxOrderBuyPriceRatio|string(decimal)|false|none||最大委托单买价限价比例 (和预言机价格相比), decimal (quote_coin_id)|
|minOrderSellPriceRatio|string(decimal)|false|none||最小委托单卖价限价比例 (和预言机价格相比), decimal (quote_coin_id)|
|maxPositionSize|string(decimal)|false|none||最大仓位数量(baseCoinId)|
|riskTierList|[[RiskTier](#schemarisktier)]|false|none||风险限额档位列表|
|defaultTakerFeeRate|string(decimal)|false|none||合约默认的taker手续费率|
|defaultMakerFeeRate|string(decimal)|false|none||合约默认的maker手续费率|
|defaultLeverage|string(decimal)|false|none||用户没有设置交易杠杆时，初始的默认开仓杠杆倍数|
|liquidateFeeRate|string(decimal)|false|none||清算费率|
|enableTrade|boolean|false|none||是否可以交易. true: 可以交易, false: 不可交易|
|enableDisplay|boolean|false|none||是否可以展示. true: 可以展示, false: 隐藏|
|enableOpenPosition|boolean|false|none||是否可以开仓. true: 可以开仓和平仓，false: 不可以开仓仅可平仓|
|fundingInterestRate|string(decimal)|false|none||综合利率默认值, 例如: 0.0003|
|fundingImpactMarginNotional|string(decimal)|false|none||深度加权买卖价计算数量, 例如: 8000|
|fundingMaxRate|string(decimal)|false|none||资金费率最大值, 例如: 0.000234|
|fundingMinRate|string(decimal)|false|none||资金费率最小值, 例如: -0.000234|
|fundingRateIntervalMin|string(decimal)|false|none||资金费率结算时间间隔(分钟，必须是60分钟的整数倍, 从UTC时间00:00开始结算) decimal|
|displayDigitMerge|string(decimal)|false|none||深度合并. 例如: "1,0.1,0.001"|
|displayMaxLeverage|string(decimal)|false|none||展示杠杆最大倍数, decimal. 例如: 20|
|displayMinLeverage|string(decimal)|false|none||展示杠杆最小倍数, decimal. 例如: 1|
|displayNewIcon|boolean|false|none||是否为新上币对|
|displayHotIcon|boolean|false|none||是否为热门币对|
|matchServerName|string|false|none||处理撮合服务名, 例如：xxx-match-server-a。 这个值一旦配置就不能再更改了，要是改的话得做好数据迁移。|
|starkExSyntheticAssetId|string(int64)|false|none||当前币对对应的混合资产id, bigint for hex str.|
|starkExResolution|string(int64)|false|none||当前币对持有数量处理精度, bigint for hex str|
|starkExOraclePriceQuorum|string(int64)|false|none||预言机价格法定数量，bigint for hex str|
|starkExOraclePriceSignedAssetId|[string]|false|none||bigint for hex str|
|starkExOraclePriceSigner|[string]|false|none||bigint for hex str|

<h2 id="tocS_Coin">Coin</h2>

<a id="schemacoin"></a>
<a id="schema_Coin"></a>
<a id="tocScoin"></a>
<a id="tocscoin"></a>

```json
{
  "coinId": "string",
  "coinName": "string",
  "stepSize": "string",
  "showStepSize": "string",
  "iconUrl": "string",
  "starkExAssetId": "string",
  "starkExResolution": "string"
}

```

货币元信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|coinId|string(int64)|false|none||货币id|
|coinName|string|false|none||货币名称|
|stepSize|string(decimal)|false|none||最小数量单位|
|showStepSize|string(decimal)|false|none||给用户显示的最小单位|
|iconUrl|string(url)|false|none||货币图标url|
|starkExAssetId|string(int64)|false|none||starkex资产id。如果为空，代表不存在|
|starkExResolution|string|false|none||starkex处理精度。如果为空，代表不存在|

<h2 id="tocS_Chain">Chain</h2>

<a id="schemachain"></a>
<a id="schema_Chain"></a>
<a id="tocSchain"></a>
<a id="tocschain"></a>

```json
{
  "chain": "string",
  "chainId": "string",
  "chainIconUrl": "string",
  "contractAddress": "string",
  "depositGasFeeLess": true,
  "feeLess": true,
  "feeRate": "string",
  "gasLess": true,
  "gasToken": "string",
  "minFee": "string",
  "rpcUrl": "string",
  "webTxUrl": "string",
  "withdrawGasFeeLess": true,
  "tokenList": [
    {
      "tokenAddress": "string",
      "decimals": "string",
      "iconUrl": "string",
      "token": "string",
      "pullOff": true,
      "withdrawEnable": true,
      "useFixedRate": true,
      "fixedRate": "string"
    }
  ],
  "txConfirm": "string",
  "blockTime": "string",
  "appRpcUrl": "string"
}

```

用于解析数据的包装类

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|chain|string|false|none||主链名|
|chainId|string(int64)|false|none||chainId|
|chainIconUrl|string|false|none||主链图标url|
|contractAddress|string|false|none||合约地址|
|depositGasFeeLess|boolean|false|none||是否收充值手续费|
|feeLess|boolean|false|none||是否免手续费|
|feeRate|string|false|none||手续费率|
|gasLess|boolean|false|none||是否收手续费|
|gasToken|string|false|none||主链代币名|
|minFee|string|false|none||提币最小手续费 如果gas+value*fee_rate 小于 min_fee, 就按照min_fee收取|
|rpcUrl|string|false|none||链的线上节点服务|
|webTxUrl|string|false|none||交易tx链接|
|withdrawGasFeeLess|boolean|false|none||是否收提币手续费|
|tokenList|[[MultiChainToken](#schemamultichaintoken)]|false|none||跨链相关币种类集合信息|
|txConfirm|string(int64)|false|none||链上充值确认数|
|blockTime|string|false|none||区块时间|
|appRpcUrl|string|false|none||none|

<h2 id="tocS_Result<GetServerTime>">Result<GetServerTime></h2>

<a id="schemaresult<getservertime>"></a>
<a id="schema_Result<GetServerTime>"></a>
<a id="tocSresult<getservertime>"></a>
<a id="tocsresult<getservertime>"></a>

```json
{
  "code": "string",
  "data": {
    "timeMillis": "string"
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
|data|[GetServerTime](#schemagetservertime)|false|none||服务器时间|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetServerTime">GetServerTime</h2>

<a id="schemagetservertime"></a>
<a id="schema_GetServerTime"></a>
<a id="tocSgetservertime"></a>
<a id="tocsgetservertime"></a>

```json
{
  "timeMillis": "string"
}

```

服务器时间

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|timeMillis|string(int64)|false|none||服务器时间戳，毫秒|

<h2 id="tocS_Result<List<OpenInterest>>">Result<List<OpenInterest>></h2>

<a id="schemaresult<list<openinterest>>"></a>
<a id="schema_Result<List<OpenInterest>>"></a>
<a id="tocSresult<list<openinterest>>"></a>
<a id="tocsresult<list<openinterest>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "timestamp": "string",
      "size": "string"
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
|data|[[OpenInterest](#schemaopeninterest)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_OpenInterest">OpenInterest</h2>

<a id="schemaopeninterest"></a>
<a id="schema_OpenInterest"></a>
<a id="tocSopeninterest"></a>
<a id="tocsopeninterest"></a>

```json
{
  "contractId": "string",
  "timestamp": "string",
  "size": "string"
}

```

持仓量

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约ID|
|timestamp|string|false|none||统计时间戳|
|size|string(int64)|false|none||持仓量|

<h2 id="tocS_Result<List<Depth>>">Result<List<Depth>></h2>

<a id="schemaresult<list<depth>>"></a>
<a id="schema_Result<List<Depth>>"></a>
<a id="tocSresult<list<depth>>"></a>
<a id="tocsresult<list<depth>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "startVersion": "string",
      "endVersion": "string",
      "level": 0,
      "contractId": "string",
      "contractName": "string",
      "asks": [
        {
          "price": "string",
          "size": "string"
        }
      ],
      "bids": [
        {
          "price": "string",
          "size": "string"
        }
      ],
      "depthType": "UNKNOWN_DEPTH_TYPE"
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
|data|[[Depth](#schemadepth)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Depth">Depth</h2>

<a id="schemadepth"></a>
<a id="schema_Depth"></a>
<a id="tocSdepth"></a>
<a id="tocsdepth"></a>

```json
{
  "startVersion": "string",
  "endVersion": "string",
  "level": 0,
  "contractId": "string",
  "contractName": "string",
  "asks": [
    {
      "price": "string",
      "size": "string"
    }
  ],
  "bids": [
    {
      "price": "string",
      "size": "string"
    }
  ],
  "depthType": "UNKNOWN_DEPTH_TYPE"
}

```

深度

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|startVersion|string(int64)|false|none||开始订单簿版本号|
|endVersion|string(int64)|false|none||结束订单簿版本号|
|level|integer(int32)|false|none||深度档位|
|contractId|string(int64)|false|none||合约id|
|contractName|string|false|none||合约名称|
|asks|[[BookOrder](#schemabookorder)]|false|none||ask列表|
|bids|[[BookOrder](#schemabookorder)]|false|none||bid列表|
|depthType|string|false|none||盘口深度类型|

#### 枚举值

|属性|值|
|---|---|
|depthType|UNKNOWN_DEPTH_TYPE|
|depthType|SNAPSHOT|
|depthType|CHANGED|
|depthType|UNRECOGNIZED|

<h2 id="tocS_BookOrder">BookOrder</h2>

<a id="schemabookorder"></a>
<a id="schema_BookOrder"></a>
<a id="tocSbookorder"></a>
<a id="tocsbookorder"></a>

```json
{
  "price": "string",
  "size": "string"
}

```

订单簿信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|price|string(decimal)|false|none||价格|
|size|string(decimal)|false|none||数量|

<h2 id="tocS_Result<PageData<Kline>>">Result<PageData<Kline>></h2>

<a id="schemaresult<pagedata<kline>>"></a>
<a id="schema_Result<PageData<Kline>>"></a>
<a id="tocSresult<pagedata<kline>>"></a>
<a id="tocsresult<pagedata<kline>>"></a>

```json
{
  "code": "string",
  "data": {
    "dataList": [
      {
        "klineId": "string",
        "contractId": "string",
        "contractName": "string",
        "klineType": "UNKNOWN_KLINE_TYPE",
        "klineTime": "string",
        "priceType": "UNKNOWN_PRICE_TYPE",
        "trades": "string",
        "size": "string",
        "value": "string",
        "high": "string",
        "low": "string",
        "open": "string",
        "close": "string",
        "makerBuySize": "string",
        "makerBuyValue": "string"
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
|data|[PageDataKline](#schemapagedatakline)|false|none||通用翻页返回|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_PageDataKline">PageDataKline</h2>

<a id="schemapagedatakline"></a>
<a id="schema_PageDataKline"></a>
<a id="tocSpagedatakline"></a>
<a id="tocspagedatakline"></a>

```json
{
  "dataList": [
    {
      "klineId": "string",
      "contractId": "string",
      "contractName": "string",
      "klineType": "UNKNOWN_KLINE_TYPE",
      "klineTime": "string",
      "priceType": "UNKNOWN_PRICE_TYPE",
      "trades": "string",
      "size": "string",
      "value": "string",
      "high": "string",
      "low": "string",
      "open": "string",
      "close": "string",
      "makerBuySize": "string",
      "makerBuyValue": "string"
    }
  ],
  "nextPageOffsetData": "string"
}

```

通用翻页返回

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dataList|[[Kline](#schemakline)]|false|none||数据列表|
|nextPageOffsetData|string|false|none||获取下一页偏移。如果没有下一页数据，则为空串|

<h2 id="tocS_Result<List<ContractKline>>">Result<List<ContractKline>></h2>

<a id="schemaresult<list<contractkline>>"></a>
<a id="schema_Result<List<ContractKline>>"></a>
<a id="tocSresult<list<contractkline>>"></a>
<a id="tocsresult<list<contractkline>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "klineList": [
        {
          "klineId": "string",
          "contractId": "string",
          "contractName": "string",
          "klineType": "UNKNOWN_KLINE_TYPE",
          "klineTime": "string",
          "priceType": "UNKNOWN_PRICE_TYPE",
          "trades": "string",
          "size": "string",
          "value": "string",
          "high": "string",
          "low": "string",
          "open": "string",
          "close": "string",
          "makerBuySize": "string",
          "makerBuyValue": "string"
        }
      ]
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
|data|[[ContractMultiKline](#schemacontractmultikline)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Kline">Kline</h2>

<a id="schemakline"></a>
<a id="schema_Kline"></a>
<a id="tocSkline"></a>
<a id="tocskline"></a>

```json
{
  "klineId": "string",
  "contractId": "string",
  "contractName": "string",
  "klineType": "UNKNOWN_KLINE_TYPE",
  "klineTime": "string",
  "priceType": "UNKNOWN_PRICE_TYPE",
  "trades": "string",
  "size": "string",
  "value": "string",
  "high": "string",
  "low": "string",
  "open": "string",
  "close": "string",
  "makerBuySize": "string",
  "makerBuyValue": "string"
}

```

K线

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|klineId|string(int64)|false|none||K线ID|
|contractId|string(int64)|false|none||永续合约id|
|contractName|string|false|none||永续合约名称|
|klineType|string|false|none||K线类型|
|klineTime|string(int64)|false|none||K线时间|
|priceType|string|false|none||K线的价格类型|
|trades|string(int64)|false|none||成交笔数|
|size|string(decimal)|false|none||成交量|
|value|string(decimal)|false|none||成交额|
|high|string(decimal)|false|none||最高价|
|low|string(decimal)|false|none||最低价|
|open|string(decimal)|false|none||内开盘价|
|close|string(decimal)|false|none||内收盘价|
|makerBuySize|string(decimal)|false|none||Maker买入成交量|
|makerBuyValue|string(decimal)|false|none||Maker买入成交额|

#### 枚举值

|属性|值|
|---|---|
|klineType|UNKNOWN_KLINE_TYPE|
|klineType|MINUTE_1|
|klineType|MINUTE_5|
|klineType|MINUTE_15|
|klineType|MINUTE_30|
|klineType|HOUR_1|
|klineType|HOUR_2|
|klineType|HOUR_4|
|klineType|HOUR_6|
|klineType|HOUR_8|
|klineType|HOUR_12|
|klineType|DAY_1|
|klineType|WEEK_1|
|klineType|MONTH_1|
|klineType|UNRECOGNIZED|
|priceType|UNKNOWN_PRICE_TYPE|
|priceType|ORACLE_PRICE|
|priceType|INDEX_PRICE|
|priceType|LAST_PRICE|
|priceType|ASK1_PRICE|
|priceType|BID1_PRICE|
|priceType|OPEN_INTEREST|
|priceType|UNRECOGNIZED|

<h2 id="tocS_ContractMultiKline">ContractMultiKline</h2>

<a id="schemacontractmultikline"></a>
<a id="schema_ContractMultiKline"></a>
<a id="tocScontractmultikline"></a>
<a id="tocscontractmultikline"></a>

```json
{
  "contractId": "string",
  "klineList": [
    {
      "klineId": "string",
      "contractId": "string",
      "contractName": "string",
      "klineType": "UNKNOWN_KLINE_TYPE",
      "klineTime": "string",
      "priceType": "UNKNOWN_PRICE_TYPE",
      "trades": "string",
      "size": "string",
      "value": "string",
      "high": "string",
      "low": "string",
      "open": "string",
      "close": "string",
      "makerBuySize": "string",
      "makerBuyValue": "string"
    }
  ]
}

```

合约多条K线

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||永续合约id|
|klineList|[[Kline](#schemakline)]|false|none||kline数据集合|

<h2 id="tocS_StatDayTrade">StatDayTrade</h2>

<a id="schemastatdaytrade"></a>
<a id="schema_StatDayTrade"></a>
<a id="tocSstatdaytrade"></a>
<a id="tocsstatdaytrade"></a>

```json
{
  "dayTime": "string",
  "totalTrades": "string",
  "totalValue": "string",
  "createTime": "string"
}

```

日交易信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|dayTime|string(int64)|false|none||日期|
|totalTrades|string(int64)|false|none||总交易笔数|
|totalValue|string|false|none||总交易额|
|createTime|string(int64)|false|none||创建时间|

<h2 id="tocS_Result<List<StatDayTrade>>">Result<List<StatDayTrade>></h2>

<a id="schemaresult<list<statdaytrade>>"></a>
<a id="schema_Result<List<StatDayTrade>>"></a>
<a id="tocSresult<list<statdaytrade>>"></a>
<a id="tocsresult<list<statdaytrade>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "dayTime": "string",
      "totalTrades": "string",
      "totalValue": "string",
      "createTime": "string"
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
|data|[[StatDayTrade](#schemastatdaytrade)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_Ticker">Ticker</h2>

<a id="schematicker"></a>
<a id="schema_Ticker"></a>
<a id="tocSticker"></a>
<a id="tocsticker"></a>

```json
{
  "contractId": "string",
  "contractName": "string",
  "priceChange": "string",
  "priceChangePercent": "string",
  "trades": "string",
  "size": "string",
  "value": "string",
  "high": "string",
  "low": "string",
  "open": "string",
  "close": "string",
  "highTime": "string",
  "lowTime": "string",
  "startTime": "string",
  "endTime": "string",
  "lastPrice": "string",
  "indexPrice": "string",
  "oraclePrice": "string",
  "openInterest": "string",
  "fundingRate": "string",
  "fundingTime": "string",
  "nextFundingTime": "string"
}

```

24小时行情

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约ID|
|contractName|string|false|none||合约名称|
|priceChange|string(decimal)|false|none||价格涨跌幅|
|priceChangePercent|string(decimal)|false|none||价格涨跌幅百分比|
|trades|string(int64)|false|none||24小时成交笔数|
|size|string(decimal)|false|none||24小时成交量|
|value|string(decimal)|false|none||24小时成交额|
|high|string(decimal)|false|none||24小时最高价|
|low|string(decimal)|false|none||24小时最低价|
|open|string(decimal)|false|none||24小时内开盘价|
|close|string(decimal)|false|none||24小时内收盘价|
|highTime|string(int64)|false|none||24小时最高价时间|
|lowTime|string(int64)|false|none||24小时最低价时间|
|startTime|string(int64)|false|none||24小时行情开始时间|
|endTime|string(int64)|false|none||24小时行情结束时间|
|lastPrice|string(decimal)|false|none||最新成交价|
|indexPrice|string(decimal)|false|none||当前指数价格|
|oraclePrice|string(decimal)|false|none||当前预言机价格|
|openInterest|string(decimal)|false|none||未平仓持仓量|
|fundingRate|string|false|none||当前已经结算的资金费率|
|fundingTime|string(int64)|false|none||资金费率结算时间|
|nextFundingTime|string(int64)|false|none||下次资金费率结算时间|

<h2 id="tocS_Result<List<Ticker>>">Result<List<Ticker>></h2>

<a id="schemaresult<list<ticker>>"></a>
<a id="schema_Result<List<Ticker>>"></a>
<a id="tocSresult<list<ticker>>"></a>
<a id="tocsresult<list<ticker>>"></a>

```json
{
  "code": "string",
  "data": [
    {
      "contractId": "string",
      "contractName": "string",
      "priceChange": "string",
      "priceChangePercent": "string",
      "trades": "string",
      "size": "string",
      "value": "string",
      "high": "string",
      "low": "string",
      "open": "string",
      "close": "string",
      "highTime": "string",
      "lowTime": "string",
      "startTime": "string",
      "endTime": "string",
      "lastPrice": "string",
      "indexPrice": "string",
      "oraclePrice": "string",
      "openInterest": "string",
      "fundingRate": "string",
      "fundingTime": "string",
      "nextFundingTime": "string"
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
|data|[[Ticker](#schematicker)]|false|none||正确响应数据|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_TickerSummary">TickerSummary</h2>

<a id="schematickersummary"></a>
<a id="schema_TickerSummary"></a>
<a id="tocStickersummary"></a>
<a id="tocstickersummary"></a>

```json
{
  "period": "UNKNOWN_PERIOD",
  "trades": "string",
  "value": "string",
  "openInterest": "string"
}

```

行情汇总

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|period|string|false|none||汇总周期|
|trades|string|false|none||交易所总交易笔数|
|value|string|false|none||总成交金额|
|openInterest|string|false|none||当前总未平仓额|

#### 枚举值

|属性|值|
|---|---|
|period|UNKNOWN_PERIOD|
|period|LAST_DAY_1|
|period|LAST_DAY_7|
|period|LAST_DAY_30|
|period|UNRECOGNIZED|

<h2 id="tocS_Result<GetTickerSummaryModel>">Result<GetTickerSummaryModel></h2>

<a id="schemaresult<gettickersummarymodel>"></a>
<a id="schema_Result<GetTickerSummaryModel>"></a>
<a id="tocSresult<gettickersummarymodel>"></a>
<a id="tocsresult<gettickersummarymodel>"></a>

```json
{
  "code": "string",
  "data": {
    "tickerSummary": {
      "period": "UNKNOWN_PERIOD",
      "trades": "string",
      "value": "string",
      "openInterest": "string"
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
|data|[GetTickerSummary](#schemagettickersummary)|false|none||获取行情汇总响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetTickerSummary">GetTickerSummary</h2>

<a id="schemagettickersummary"></a>
<a id="schema_GetTickerSummary"></a>
<a id="tocSgettickersummary"></a>
<a id="tocsgettickersummary"></a>

```json
{
  "tickerSummary": {
    "period": "UNKNOWN_PERIOD",
    "trades": "string",
    "value": "string",
    "openInterest": "string"
  }
}

```

获取行情汇总响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|tickerSummary|[TickerSummary](#schematickersummary)|false|none||行情汇总|

<h2 id="tocS_Result<CheckUserExist>">Result<CheckUserExist></h2>

<a id="schemaresult<checkuserexist>"></a>
<a id="schema_Result<CheckUserExist>"></a>
<a id="tocSresult<checkuserexist>"></a>
<a id="tocsresult<checkuserexist>"></a>

```json
{
  "code": "string",
  "data": {
    "isUserExist": true
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
|data|[CheckUserExist](#schemacheckuserexist)|false|none||判断用户是否存在-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CheckUserExist">CheckUserExist</h2>

<a id="schemacheckuserexist"></a>
<a id="schema_CheckUserExist"></a>
<a id="tocScheckuserexist"></a>
<a id="tocscheckuserexist"></a>

```json
{
  "isUserExist": true
}

```

判断用户是否存在-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|isUserExist|boolean|false|none||用户是否存在|

<h2 id="tocS_Result<GetAppScanSecret>">Result<GetAppScanSecret></h2>

<a id="schemaresult<getappscansecret>"></a>
<a id="schema_Result<GetAppScanSecret>"></a>
<a id="tocSresult<getappscansecret>"></a>
<a id="tocsresult<getappscansecret>"></a>

```json
{
  "code": "string",
  "data": {
    "secret": "string"
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
|data|[GetAppScanSecret](#schemagetappscansecret)|false|none||获取AppScanSecret响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_GetAppScanSecret">GetAppScanSecret</h2>

<a id="schemagetappscansecret"></a>
<a id="schema_GetAppScanSecret"></a>
<a id="tocSgetappscansecret"></a>
<a id="tocsgetappscansecret"></a>

```json
{
  "secret": "string"
}

```

获取AppScanSecret响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|secret|string|false|none||secret，base64 url格式|

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

取消账户下所有委托单请求参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|filterCoinIdList|[string]|false|none||过滤取消对应抵押品coinId对应的活动委托单，如果为空则取消所有抵押品coinId的活动委托单|
|filterContractIdList|[string]|false|none||过滤取消对应合约的活动委托单，如果为空则取消所有合约的活动委托单|
|filterOrderTypeList|[string]|false|none||过滤取消指定类型的委托单，不填的话所有类型委托单|
|filterOrderStatusList|[string]|false|none||过滤取消指定状态的委托单，不填的话所有状态委托单|
|filterIsPositionTpsl|[boolean]|false|none||过滤只取消对应的仓位止盈止损单，如果为空的话会取消所有合约委托单|

<h2 id="tocS_Result<CancelOrderByClientOrderId>">Result<CancelOrderByClientOrderId></h2>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[CancelOrderByClientOrderId](#schemacancelorderbyclientorderid)|false|none||根据ClientOrderId撤销订单响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

根据ClientOrderId撤销订单响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|cancelResultMap|object|false|none||none|
|» **additionalProperties**|string|false|none||none|

#### 枚举值

|属性|值|
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

根据clientId取消委托单请求参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|clientOrderIdList|[string]|true|none||委托单 client order id|

<h2 id="tocS_Result<CancelOrder>">Result<CancelOrder></h2>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[CancelOrder](#schemacancelorder)|false|none||撤销订单响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

撤销订单响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|cancelResultMap|object|false|none||none|
|» **additionalProperties**|string|false|none||none|

#### 枚举值

|属性|值|
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

取消委托单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|orderIdList|[string]|true|none||委托单id|

<h2 id="tocS_Result<CreateOrder>">Result<CreateOrder></h2>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[CreateOrder](#schemacreateorder)|false|none||创建订单响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

创建订单响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|orderId|string(int64)|false|none||委托单Id|

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

开仓止盈止损参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|side|string|false|none||买卖方向,此字段必填|
|price|string|false|none||委托价格(最差可接受的价格), 实际为decimal类型。此字段必填，市价单时填0|
|size|string|false|none||委托数量, 实际为decimal类型。此字段必填|
|clientOrderId|string|false|none||客户自定义id，用于签名&幂等校验。此字段必填|
|triggerPrice|string|false|none||触发价格。此字段必填|
|triggerPriceType|string|false|none||价格类型。最新市价[默认],标记价格。此字段必填。|
|expireTime|string(int64)|false|none||过期时间。|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_order_id) 前32个bit|
|l2Value|string|false|none||l2签名委托价值(实际成交价必须等于或优于 l2_value / l2_price), 与 price x size 的值可能不一样。实际为decimal类型|
|l2Size|string|false|none||l2签名委托数量, 与size字段可能不一样。实际为decimal类型|
|l2LimitFee|string|false|none||l2签名最高可以接受的下单费用|
|l2ExpireTime|string|false|none||l2签名过期时间. unix时间的小时数，至少要比 expire_time 晚10个小时|
|l2Signature|string|false|none||l2签名|

#### 枚举值

|属性|值|
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

创建委托单-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|contractId|string(int64)|false|none||所属合约id|
|side|string|false|none||买卖方向。此字段必填|
|size|string|false|none||委托数量, 实际为decimal类型。此字段必填|
|price|string|false|none||委托价格(最差可接受的价格), 实际为decimal类型。此字段必填，市价单填0即可。|
|clientOrderId|string|false|none||客户自定义id，用于幂等校验。此字段必填|
|type|string|false|none||委托单类型。此字段必填|
|timeInForce|string|false|none||委托单执行策略。type为 LIMIT/STOP_LIMIT/TAKE_PROFIT_LIMIT 时有意义。此字段必填，市价单必为IMMEDIATE_OR_CANCEL。|
|reduceOnly|boolean|false|none||是否是只减仓委托。此字段必填|
|triggerPrice|string|false|none||触发价格。type为 STOP_LIMIT/STOP_MARKET/TAKE_PROFIT_LIMIT/TAKE_PROFIT_MARKET 时有意义。如果为0代表字段为空。实际为decimal类型。当为条件单时必填。|
|triggerPriceType|string|false|none||价格类型。最新市价[默认],标记价格。type为条件单时有意义。当为条件单时必填。|
|expireTime|string(int64)|false|none||过期时间。|
|sourceKey|string|false|none||来源key，uuid|
|isPositionTpsl|boolean|false|none||是否为仓位止盈止损单。此字段必填，默认为false|
|openTpslParentOrderId|string(int64)|false|none||开仓止盈单，止损单的开仓单orderId|
|isSetOpenTp|boolean|false|none||是否设置开仓止盈。此字段必填|
|openTp|[OpenTpSlParam](#schemaopentpslparam)|false|none||开仓止盈止损参数|
|isSetOpenSl|boolean|false|none||是否设置开仓止损。此字段必填|
|openSl|[OpenTpSlParam](#schemaopentpslparam)|false|none||开仓止盈止损参数|
|l2Nonce|string(int64)|false|none||l2签名nonce。取sha256(client_order_id) 前32个bit|
|l2Value|string|false|none||l2签名委托价值(实际成交价必须等于或优于 l2_value / l2_price), 与 price x size 的值可能不一样。实际为decimal类型|
|l2Size|string|false|none||l2签名委托数量, 与size字段可能不一样。实际为decimal类型|
|l2LimitFee|string|false|none||l2签名最高可以接受的下单费用|
|l2ExpireTime|string(int64)|false|none||l2签名过期时间，单位毫秒。参与签名生成/校验时要取小时数，即 l2_expire_time / 3600000。注意此字段必须要大于等于 expire_time + 8 * 24 * 60 * 60 * 1000(8天)|
|l2Signature|string|false|none||l2签名|
|extraType|string|false|none||附加类型，供上层业务使用|
|extraDataJson|string|false|none||额外数据，json格式，默认为空串|

#### 枚举值

|属性|值|
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

<h2 id="tocS_Result<GetMaxCreateOrderSize>">Result<GetMaxCreateOrderSize></h2>

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

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|string|false|none||状态码.成功返回为"SUCCESS",其他都为失败|
|data|[GetMaxCreateOrderSize](#schemagetmaxcreateordersize)|false|none||获取最大下单数量-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

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

获取最大下单数量-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|maxBuySize|string(decimal)|false|none||最大买入size|
|maxSellSize|string(decimal)|false|none||最大卖出size|
|ask1Price|string(decimal)|false|none||最优askPrice|
|bid1Price|string(decimal)|false|none||最优bidPrice|

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

获取最大下单数量-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|accountId|string(int64)|false|none||账户id|
|contractId|string(int64)|false|none||所属合约id|
|price|string|false|none||下单价格|

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

<h2 id="tocS_Result<CreateAppScanSecret>">Result<CreateAppScanSecret></h2>

<a id="schemaresult<createappscansecret>"></a>
<a id="schema_Result<CreateAppScanSecret>"></a>
<a id="tocSresult<createappscansecret>"></a>
<a id="tocsresult<createappscansecret>"></a>

```json
{
  "code": "string",
  "data": {
    "token": "string",
    "secret": "string"
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
|data|[CreateAppScanSecret](#schemacreateappscansecret)|false|none||创建AppScanSecret响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_CreateAppScanSecret">CreateAppScanSecret</h2>

<a id="schemacreateappscansecret"></a>
<a id="schema_CreateAppScanSecret"></a>
<a id="tocScreateappscansecret"></a>
<a id="tocscreateappscansecret"></a>

```json
{
  "token": "string",
  "secret": "string"
}

```

创建AppScanSecret响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|token|string|false|none||token|
|secret|string|false|none||secret，base64 url格式|

<h2 id="tocS_CreateAppScanSecretParam">CreateAppScanSecretParam</h2>

<a id="schemacreateappscansecretparam"></a>
<a id="schema_CreateAppScanSecretParam"></a>
<a id="tocScreateappscansecretparam"></a>
<a id="tocscreateappscansecretparam"></a>

```json
{
  "expireTime": "string"
}

```

创建AppScanSecret请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|expireTime|string|false|none||过期时间戳，单位毫秒|

<h2 id="tocS_ReadSiteMessageParam">ReadSiteMessageParam</h2>

<a id="schemareadsitemessageparam"></a>
<a id="schema_ReadSiteMessageParam"></a>
<a id="tocSreadsitemessageparam"></a>
<a id="tocsreadsitemessageparam"></a>

```json
{
  "messageIdList": [
    "string"
  ]
}

```

标识阅读站内信消息-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|messageIdList|[string]|false|none||消息Id. 可传多个。不传全部已读|

<h2 id="tocS_UpdateUserPreferenceParam">UpdateUserPreferenceParam</h2>

<a id="schemaupdateuserpreferenceparam"></a>
<a id="schema_UpdateUserPreferenceParam"></a>
<a id="tocSupdateuserpreferenceparam"></a>
<a id="tocsupdateuserpreferenceparam"></a>

```json
{
  "isSharingEthAddress": true,
  "isSharingNickname": true,
  "isEmailNotifyGeneralEnable": true,
  "isEmailNotifyTradingEnable": true,
  "isEmailNotifyAccountEnable": true,
  "isAppNotifyTradingEnable": true
}

```

更新用户设置-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|isSharingEthAddress|boolean|false|none||是否将 eth address 展示给其他用户，如排行榜等，如果为否则中间部分会以 *** 展示|
|isSharingNickname|boolean|false|none||是否将 nickname 展示给其他用户，如排行榜等，如果为否则中间部分会以 *** 展示|
|isEmailNotifyGeneralEnable|boolean|false|none||Newsletter, Market Updates, Product Updates|
|isEmailNotifyTradingEnable|boolean|false|none||Deposits、Withdrawals, Account updates|
|isEmailNotifyAccountEnable|boolean|false|none||Order Updates and Liquidation updates|
|isAppNotifyTradingEnable|boolean|false|none||App push|

<h2 id="tocS_UpdateUserParam">UpdateUserParam</h2>

<a id="schemaupdateuserparam"></a>
<a id="schema_UpdateUserParam"></a>
<a id="tocSupdateuserparam"></a>
<a id="tocsupdateuserparam"></a>

```json
{
  "nickname": "string",
  "email": "string",
  "country": "string",
  "language": "string"
}

```

更新用户信息-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|nickname|string|false|none||昵称|
|email|string|false|none||邮箱|
|country|string|false|none||国家码|
|language|string|false|none||语言|

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

<h2 id="tocS_ForcePushPriceParam">ForcePushPriceParam</h2>

<a id="schemaforcepushpriceparam"></a>
<a id="schema_ForcePushPriceParam"></a>
<a id="tocSforcepushpriceparam"></a>
<a id="tocsforcepushpriceparam"></a>

```json
{
  "contractId": "string",
  "price": "string"
}

```

按照某个指定价格作为预言机价格推送-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|contractId|string(int64)|false|none||合约id|
|price|string|false|none||价格|

<h2 id="tocS_NotifyTxRejectResult">NotifyTxRejectResult</h2>

<a id="schemanotifytxrejectresult"></a>
<a id="schema_NotifyTxRejectResult"></a>
<a id="tocSnotifytxrejectresult"></a>
<a id="tocsnotifytxrejectresult"></a>

```json
{
  "alt_txs": [
    {}
  ]
}

```

通知交易被拒绝结果

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|alt_txs|[[JsonNode](#schemajsonnode)]|false|none||替换交易列表|

<h2 id="tocS_NotifyTxRejectParam">NotifyTxRejectParam</h2>

<a id="schemanotifytxrejectparam"></a>
<a id="schema_NotifyTxRejectParam"></a>
<a id="tocSnotifytxrejectparam"></a>
<a id="tocsnotifytxrejectparam"></a>

```json
{
  "tx_id": 0,
  "reason_code": "string",
  "reason_msg": "string",
  "tx": {}
}

```

通知交易被拒绝参数

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|tx_id|integer(int64)|false|none||交易id|
|reason_code|string|false|none||拒绝错误码|
|reason_msg|string|false|none||拒绝错误原因|
|tx|[JsonNode](#schemajsonnode)|false|none||替换交易列表|

<h2 id="tocS_JsonNode">JsonNode</h2>

<a id="schemajsonnode"></a>
<a id="schema_JsonNode"></a>
<a id="tocSjsonnode"></a>
<a id="tocsjsonnode"></a>

```json
{}

```

替换交易列表

### 属性

*None*

<h2 id="tocS_UserPreference">UserPreference</h2>

<a id="schemauserpreference"></a>
<a id="schema_UserPreference"></a>
<a id="tocSuserpreference"></a>
<a id="tocsuserpreference"></a>

```json
{
  "userId": "string",
  "isSharingEthAddress": true,
  "isSharingNickname": true,
  "isEmailNotifyGeneralEnable": true,
  "isEmailNotifyTradingEnable": true,
  "isEmailNotifyAccountEnable": true,
  "isAppNotifyTradingEnable": true,
  "createdTime": "string",
  "updatedTime": "string"
}

```

用户设置

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string(int64)|false|none||用户id|
|isSharingEthAddress|boolean|false|none||是否分享ETH地址|
|isSharingNickname|boolean|false|none||是否分享昵称|
|isEmailNotifyGeneralEnable|boolean|false|none||是否启用通用通知邮件|
|isEmailNotifyTradingEnable|boolean|false|none||是否启用交易通知邮件|
|isEmailNotifyAccountEnable|boolean|false|none||是否启用账户通知邮件|
|isAppNotifyTradingEnable|boolean|false|none||是否启用交易通知App推送|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

<h2 id="tocS_User">User</h2>

<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "id": "string",
  "ethAddress": "string",
  "nickname": "string",
  "email": "string",
  "isEmailVerified": true,
  "country": "string",
  "language": "string",
  "avatarUrl": "string",
  "avatarBorderUrl": "string",
  "createdTime": "string",
  "updatedTime": "string"
}

```

用户信息

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|string(int64)|false|none||用户id|
|ethAddress|string|false|none||ETH地址|
|nickname|string|false|none||昵称|
|email|string|false|none||邮箱|
|isEmailVerified|boolean|false|none||邮箱验证状态|
|country|string|false|none||国家码|
|language|string|false|none||语言|
|avatarUrl|string|false|none||头像URL|
|avatarBorderUrl|string|false|none||头像边框URL|
|createdTime|string(int64)|false|none||创建时间|
|updatedTime|string(int64)|false|none||更新时间|

<h2 id="tocS_Result<OnboardSite>">Result<OnboardSite></h2>

<a id="schemaresult<onboardsite>"></a>
<a id="schema_Result<OnboardSite>"></a>
<a id="tocSresult<onboardsite>"></a>
<a id="tocsresult<onboardsite>"></a>

```json
{
  "code": "string",
  "data": {
    "user": {
      "id": "string",
      "ethAddress": "string",
      "nickname": "string",
      "email": "string",
      "isEmailVerified": true,
      "country": "string",
      "language": "string",
      "avatarUrl": "string",
      "avatarBorderUrl": "string",
      "createdTime": "string",
      "updatedTime": "string"
    },
    "userPreference": {
      "userId": "string",
      "isSharingEthAddress": true,
      "isSharingNickname": true,
      "isEmailNotifyGeneralEnable": true,
      "isEmailNotifyTradingEnable": true,
      "isEmailNotifyAccountEnable": true,
      "isAppNotifyTradingEnable": true,
      "createdTime": "string",
      "updatedTime": "string"
    },
    "isNewUser": true
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
|data|[OnboardSite](#schemaonboardsite)|false|none||用户登录站点-响应|
|errorParam|object|false|none||错误消息中的参数信息|
|» **additionalProperties**|string|false|none||错误消息中的参数信息|
|requestTime|string(timestamp)|false|none||服务器请求接收时间|
|responseTime|string(timestamp)|false|none||服务器响应返回时间|
|traceId|string|false|none||调用traceId|

<h2 id="tocS_OnboardSite">OnboardSite</h2>

<a id="schemaonboardsite"></a>
<a id="schema_OnboardSite"></a>
<a id="tocSonboardsite"></a>
<a id="tocsonboardsite"></a>

```json
{
  "user": {
    "id": "string",
    "ethAddress": "string",
    "nickname": "string",
    "email": "string",
    "isEmailVerified": true,
    "country": "string",
    "language": "string",
    "avatarUrl": "string",
    "avatarBorderUrl": "string",
    "createdTime": "string",
    "updatedTime": "string"
  },
  "userPreference": {
    "userId": "string",
    "isSharingEthAddress": true,
    "isSharingNickname": true,
    "isEmailNotifyGeneralEnable": true,
    "isEmailNotifyTradingEnable": true,
    "isEmailNotifyAccountEnable": true,
    "isAppNotifyTradingEnable": true,
    "createdTime": "string",
    "updatedTime": "string"
  },
  "isNewUser": true
}

```

用户登录站点-响应

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|user|[User](#schemauser)|false|none||用户信息|
|userPreference|[UserPreference](#schemauserpreference)|false|none||用户设置|
|isNewUser|boolean|false|none||是否新用户第一次注册|

<h2 id="tocS_OnboardSiteParam">OnboardSiteParam</h2>

<a id="schemaonboardsiteparam"></a>
<a id="schema_OnboardSiteParam"></a>
<a id="tocSonboardsiteparam"></a>
<a id="tocsonboardsiteparam"></a>

```json
{
  "ethAddress": "string",
  "onlySignOn": "string",
  "param": "string",
  "signature": "string",
  "l2Key": "string",
  "l2KeyYCoordinate": "string",
  "clientAccountId": "string"
}

```

用户登录站点-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|ethAddress|string|false|none||eth地址|
|onlySignOn|string|false|none||only_sign_on|
|param|string|false|none||参数|
|signature|string|false|none||签名|
|l2Key|string|false|none||创建默认账户参数: L2上的账户key，保证全局唯一。对应starkEx中的starkKey。bigint for hex str|
|l2KeyYCoordinate|string|false|none||创建默认账户参数: 只用于验证 l2Signature 是否ok。不返回给C端用户。bigint for hex str|
|clientAccountId|string|false|none||创建默认账户参数: 客户端账户id, 用于幂等性校验|

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

<h2 id="tocS_VerifyEmailParam">VerifyEmailParam</h2>

<a id="schemaverifyemailparam"></a>
<a id="schema_VerifyEmailParam"></a>
<a id="tocSverifyemailparam"></a>
<a id="tocsverifyemailparam"></a>

```json
{
  "userId": "string",
  "token": "string"
}

```

验证邮箱-请求

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string|true|none||验证邮件链接的userId|
|token|string|true|none||验证邮件链接的token|

