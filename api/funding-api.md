# test

> v1.0.0

Base URLs:

# 01.FundingPublicApi

<a id="opIdgetLatestFundingRate"></a>

## GET Get Latest Funding Rate by Contract ID

GET /api/v1/public/funding/getLatestFundingRate

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|contractId|query|string| No |Contract ID|

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

### Response Codes

|Status Code|Status Code Description|Description|Data Model|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

<a id="opIdgetFundingRatePage"></a>

## GET Get Funding Rate History by Contract ID with Pagination

GET /api/v1/public/funding/getFundingRatePage

### Request Parameters

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|contractId|query|string| No |Contract ID|
|size|query|string| No |Number of items to retrieve. Must be greater than 0 and less than or equal to 100|
|offsetData|query|string| No |Pagination offset. If not provided or empty, retrieves the first page|
|filterSettlementFundingRate|query|string| No |If true, only query settlement funding rates (funding rate settlement occurs every 8 hours, with a predicted funding rate calculated every minute)|
|filterBeginTimeInclusive|query|string| No |Start time. If not provided, retrieves the oldest data|
|filterEndTimeExclusive|query|string| No |End time. If not provided, retrieves the latest data|

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

### Response Codes

|Status Code|Status Code Description|Description|Data Model|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|default response|[Result](#schemaresult)|

# Data Models

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise indicates failure|
|data|[PageDataFundingRate](#schemapagedatafundingrate)|false|none|General pagination response|
|errorParam|object|false|none|Parameter information in the error message|
|» **additionalProperties**|string|false|none|Parameter information in the error message|
|requestTime|string(timestamp)|false|none|Server request reception time|
|responseTime|string(timestamp)|false|none|Server response time|
|traceId|string|false|none|Call trace ID|

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

General pagination response

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|dataList|[[FundingRate](#schemafundingrate)]|false|none|Data list|
|nextPageOffsetData|string|false|none|Offset data to retrieve the next page. Empty string if there is no next page|

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

Funding rate

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|contractId|string(int64)|false|none|Contract ID|
|fundingTime|string(int64)|false|none|Funding rate settlement time. E.g., the funding rate for the 08:00-09:00 period is calculated from the previous 07:00-08:00 data, finalized at 08:00, and used for settlement at 09:00|
|fundingTimestamp|string(int64)|false|none|Funding rate calculation time in milliseconds|
|oraclePrice|string|false|none|Oracle price|
|indexPrice|string|false|none|Index price|
|fundingRate|string|false|none|Funding rate|
|isSettlement|boolean|false|none|Funding rate settlement flag|
|forecastFundingRate|string|false|none|Forecast funding rate|
|previousFundingRate|string|false|none|Previous funding rate|
|previousFundingTimestamp|string(int64)|false|none|Previous funding rate calculation time in milliseconds|
|premiumIndex|string|false|none|Premium index|
|avgPremiumIndex|string|false|none|Average premium index|
|premiumIndexTimestamp|string|false|none|Premium index calculation time|
|impactMarginNotional|string|false|none|Quantity required for deep weighted buy/sell price calculation|
|impactAskPrice|string|false|none|Deep weighted ask price|
|impactBidPrice|string|false|none|Deep weighted bid price|
|interestRate|string|false|none|Fixed interest rate|
|predictedFundingRate|string|false|none|Comprehensive interest rate (interestRate/frequency)|
|fundingRateIntervalMin|string(int64)|false|none|Funding rate time interval in minutes|
|starkExFundingIndex|string|false|none|StarkEx funding index|

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

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise indicates failure|
|data|[[FundingRate](#schemafundingrate)]|false|none|Successful response data|
|errorParam|object|false|none|Parameter information in the error message|
|» **additionalProperties**|string|false|none|Parameter information in the error message|
|requestTime|string(timestamp)|false|none|Server request reception time|
|responseTime|string(timestamp)|false|none|Server response time|
|traceId|string|false|none|Call trace ID|

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

General response structure

### Properties

|Name|Type|Required|Constraints|Description|
|---|---|---|---|---|
|code|string|false|none|Status code. "SUCCESS" for success, otherwise indicates failure|
|msg|string|false|none|Detailed error message when an error occurs|
|requestTime|string(int64)|false|none|Server request reception time|
|responseTime|string(int64)|false|none|Server response time|
