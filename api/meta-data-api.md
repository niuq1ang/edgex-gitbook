# MetaDataPublicApi

<a id="opIdgetServerTime"></a>

## GET Server Time

GET /api/v1/public/meta/getServerTime

> Example Response

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response Body

|Status Code|Status Code Description|Description|Data Model|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#getservertime)|

<a id="opIdgetMetaData"></a>

## GET Meta Data

GET /api/v1/public/meta/getMetaData

> Example Response

> 200 Response

```json
{
  "code": "string",
  "msg": "string",
  "requestTime": "string",
  "responseTime": "string"
}
```

### Response Body

|Status Code|Status Code Description|Description|Data Model|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#MetadataResult)|

# Data Models


<a id="MetadataResult"></a>
### MetadataResult

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, others for failure.|
|data|[MetaData](#schemametadata)|false|none|Global metadata|
|errorParam|object|false|none|Parameter information in error message|
|requestTime|string(timestamp)|false|none|Server request receiving time|
|responseTime|string(timestamp)|false|none|Server response returning time|
|traceId|string|false|none|Call traceId|



<a id="schemametadata"></a>
### Global metadata

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|global|[Global](#schemaglobal)|false|none|Global meta information|
|coinList|[[Coin](#schemacoin)]|false|none|All coin meta information|
|contractList|[[Contract](#schemacontract)]|false|none|All contract meta information|
|multiChain|[MultiChain](#schemamultichain)|false|none|Cross-chain withdrawal related class|



<a id="schemamultichain"></a>
### Cross-chain withdrawal related class

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|coinId|string(int64)|false|none|Asset id for deposit and withdrawal|
|maxWithdraw|string|false|none|Maximum withdrawal amount|
|minWithdraw|string|false|none|Minimum withdrawal amount|
|minDeposit|string|false|none|Minimum deposit amount|
|chainList|[[Chain](#schemachain)]|false|none|Supported chains|


<a id="schemachain"></a>
### Wrapper class for parsing data

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|chain|string|false|none|Main chain name|
|chainId|string(int64)|false|none|chainId|
|chainIconUrl|string|false|none|Main chain icon url|
|contractAddress|string|false|none|Contract address|
|depositGasFeeLess|boolean|false|none|Whether to charge deposit fee|
|feeLess|boolean|false|none|Whether to exempt from fees|
|feeRate|string|false|none|Fee rate|
|gasLess|boolean|false|none|Whether to charge gas fee|
|gasToken|string|false|none|Main chain token name|
|minFee|string|false|none|Minimum withdrawal fee. If gas + value*fee_rate is less than min_fee, it will be charged according to min_fee|
|rpcUrl|string|false|none|Online node service of the chain|
|webTxUrl|string|false|none|Transaction tx link|
|withdrawGasFeeLess|boolean|false|none|Whether to charge withdrawal fee|
|tokenList|[[MultiChainToken](#schemamultichaintoken)]|false|none|Collection of cross-chain related token information|
|txConfirm|string(int64)|false|none|Number of confirmations for on-chain deposit|
|blockTime|string|false|none|Block time|
|appRpcUrl|string|false|none|none|


<a id="schemamultichaintoken"></a>
### Cross-chain related token types

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|tokenAddress|string|false|none|Token contract address|
|decimals|string(int64)|false|none|Token precision|
|iconUrl|string|false|none|Token icon url|
|token|string|false|none|Token name|
|pullOff|boolean|false|none|Whether to delist, default is false|
|withdrawEnable|boolean|false|none|Whether to support withdrawal of this type of asset|
|useFixedRate|boolean|false|none|Whether to use a fixed exchange rate|
|fixedRate|string|false|none|Fixed exchange rate|



<a id="schemacontract"></a>
### Perpetual contract meta information

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|contractId|string(int64)|false|none|Perpetual contract pair identifier|
|contractName|string|false|none|Perpetual contract pair name|
|baseCoinId|string(int64)|false|none|e.g., 10000001 (BTC)|
|quoteCoinId|string(int64)|false|none|e.g., 1001 (USD/USDT)|
|tickSize|string(decimal)|false|none|Minimum price increment (quoteCoinId)|
|stepSize|string(decimal)|false|none|Minimum quantity increment (baseCoinId)|
|minOrderSize|string(decimal)|false|none|Minimum order quantity (baseCoinId)|
|maxOrderSize|string(decimal)|false|none|Maximum order quantity (baseCoinId)|
|maxOrderBuyPriceRatio|string(decimal)|false|none|Maximum limit buy order price ratio (compared to oracle price), decimal (quote_coin_id)|
|minOrderSellPriceRatio|string(decimal)|false|none|Minimum limit sell order price ratio (compared to oracle price), decimal (quote_coin_id)|
|maxPositionSize|string(decimal)|false|none|Maximum position quantity (baseCoinId)|
|riskTierList|[[RiskTier](#schemarisktier)]|false|none|List of risk limit tiers|
|defaultTakerFeeRate|string(decimal)|false|none|Default taker fee rate for the contract|
|defaultMakerFeeRate|string(decimal)|false|none|Default maker fee rate for the contract|
|defaultLeverage|string(decimal)|false|none|Initial default leverage multiplier when user has not set a trading leverage|
|liquidateFeeRate|string(decimal)|false|none|Liquidation fee rate|
|enableTrade|boolean|false|none|Whether trading is allowed. true: allowed, false: not allowed|
|enableDisplay|boolean|false|none|Whether to display. true: display, false: hide|
|enableOpenPosition|boolean|false|none|Whether opening positions is allowed. true: allowed to open and close, false: only allowed to close positions|
|fundingInterestRate|string(decimal)|false|none|Default value of overall interest rate, e.g., 0.0003|
|fundingImpactMarginNotional|string(decimal)|false|none|Quantity for calculating depth-weighted bid/ask price, e.g., 8000|
|fundingMaxRate|string(decimal)|false|none|Maximum funding rate, e.g., 0.000234|
|fundingMinRate|string(decimal)|false|none|Minimum funding rate, e.g., -0.000234|
|fundingRateIntervalMin|string(decimal)|false|none|Settlement interval of funding rate (in minutes, must be an integer multiple of 60 minutes, settlement starts from 00:00 UTC) decimal|
|displayDigitMerge|string(decimal)|false|none|Depth merge. e.g., "1,0.1,0.001"|
|displayMaxLeverage|string(decimal)|false|none|Maximum leverage multiplier to display, decimal. e.g., 20|
|displayMinLeverage|string(decimal)|false|none|Minimum leverage multiplier to display, decimal. e.g., 1|
|displayNewIcon|boolean|false|none|Whether it is a newly listed pair|
|displayHotIcon|boolean|false|none|Whether it is a hot pair|
|matchServerName|string|false|none|Matching service name, e.g., xxx-match-server-a. This value cannot be changed once configured, otherwise data migration is required.|
|starkExSyntheticAssetId|string(int64)|false|none|Synthetic asset id of the current pair, bigint for hex str.|
|starkExResolution|string(int64)|false|none|Processing precision of the quantity held by the current pair, bigint for hex str|
|starkExOraclePriceQuorum|string(int64)|false|none|Legal number of oracle prices, bigint for hex str|
|starkExOraclePriceSignedAssetId|[string]|false|none|bigint for hex str|
|starkExOraclePriceSigner|[string]|false|none|bigint for hex str|


<a id="schemarisktier"></a>
### Risk limit tier information

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|tier|integer(int32)|false|none|Tier, starting from 1|
|positionValueUpperBound|string(decimal)|false|none|Upper limit of position value for the tier (inclusive)|
|maxLeverage|string(decimal)|false|none|Maximum available leverage for the tier|
|maintenanceMarginRate|string(decimal)|false|none|Maintenance margin rate for the tier (only for display, the actual maintenance margin rate used is stark_ex_risk / 2^32 as an accurate maintenance margin rate), decimal|
|starkExRisk|string(int64)|false|none|1 ≤ risk < 2^32|
|starkExUpperBound|string(int64)|false|none|bigint. 0 ≤ upper_bound ≤ 2^128-1|



<a id="schemacoin"></a>
### Coin meta information

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|coinId|string(int64)|false|none|Coin id|
|coinName|string|false|none|Coin name|
|stepSize|string(decimal)|false|none|Minimum quantity unit|
|showStepSize|string(decimal)|false|none|Minimum unit displayed to the user|
|iconUrl|string(url)|false|none|Coin icon url|
|starkExAssetId|string(int64)|false|none|starkex asset id. If empty, it means it does not exist|
|starkExResolution|string|false|none|starkex processing precision. If empty, it means it does not exist|

<a id="schemaglobal"></a>
### Global meta information

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|appName|string|false|none|xxx|
|appEnv|string|false|none|dev/testnet/mainnet|
|appOnlySignOn|string|false|none|https://xxx.exchange|
|feeAccountId|string(int64)|false|none|Fee account id|
|feeAccountL2Key|string|false|none|Fee account l2Key, bigint for hex str|
|poolAccountId|string(int64)|false|none|Asset pool account id|
|poolAccountL2Key|string|false|none|Asset pool account l2Key, bigint for hex str|
|fastWithdrawAccountId|string(int64)|false|none|Fast withdrawal account id|
|fastWithdrawAccountL2Key|string|false|none|Fast withdrawal account l2Key, bigint for hex str|
|fastWithdrawMaxAmount|string|false|none|Maximum amount for fast withdrawal|
|fastWithdrawRegistryAddress|string|false|none|Fast withdrawal account address|
|starkExChainId|string|false|none|Chain id of starkex. bigint for hex str|
|starkExContractAddress|string|false|none|starkex contract address.|
|starkExCollateralCoin|[Coin](#schemacoin)|false|none|Coin meta information|
|starkExMaxFundingRate|integer(int32)|false|none|Maximum funding rate per second after starkex precision processing. i.e. stark_ex_max_funding_rate * 2^32 is the actual maximum funding rate per second. E.g.: 1120|
|starkExOrdersTreeHeight|integer(int32)|false|none|Order merkle tree height. E.g.: 64|
|starkExPositionsTreeHeight|integer(int32)|false|none|Account merkle tree height. E.g.: 64|
|starkExFundingValidityPeriod|integer(int32)|false|none|Funding rate submission validity period in seconds. E.g.: 86400|
|starkExPriceValidityPeriod|integer(int32)|false|none|Oracle price submission validity period in seconds. E.g.: 86400|
|maintenanceReason|string|false|none|Maintenance reason, empty if no maintenance|



<a id="getservertime"></a>
### GetServerTime

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, others for failure.|
|data|[GetServerTime](#schemagetservertime)|false|none|Server time|
|errorParam|object|false|none|Parameter information in error message|
|requestTime|string(timestamp)|false|none|Server request receiving time|
|responseTime|string(timestamp)|false|none|Server response returning time|
|traceId|string|false|none|Call traceId|


### Server time

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|timeMillis|string(int64)|false|none|Server timestamp, milliseconds|


