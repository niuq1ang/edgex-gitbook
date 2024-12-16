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

# 数据模型

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

