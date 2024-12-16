---

# Test

> v1.0.0

Base URLs:

# 01. QuotePublicApi

<a id="opIdgetTicketSummary"></a>

## GET Get Quote Summary

GET /api/v1/public/quote/getTicketSummary

### Request Parameters

| Name | Location | Type   | Required | Description   |
|------|----------|--------|----------|---------------|
| period | query    | string | No       | Summary period |

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

### Response

| Status Code | Status Code Meaning     | Description       | Data Model      |
|-------------|-------------------------|-------------------|-----------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult) |

<a id="opIdgetTicker"></a>

## GET Query 24-Hour Quotes

GET /api/v1/public/quote/getTicker

### Request Parameters

| Name       | Location | Type   | Required | Description   |
|------------|----------|--------|----------|---------------|
| contractId | query    | string | No       | Contract ID   |

> Response Example

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

### Response

| Status Code | Status Code Meaning     | Description       | Data Model |
|-------------|-------------------------|-------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | Inline |

### Response Data Structure

<a id="opIdgetStatDayTrade"></a>

## GET Get Daily Trading Statistics

GET /api/v1/public/quote/getStatDayTrade

### Request Parameters

| Name                    | Location | Type   | Required | Description                                 |
|-------------------------|----------|--------|----------|---------------------------------------------|
| startDayTimeInclusive   | query    | string | No       | Filter to get trade statistics from the specified start time |
| endDayTimeExclusive     | query    | string | No       | Filter to get daily trade statistics up to the specified end time |

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

### Response

| Status Code | Status Code Meaning     | Description       | Data Model      |
|-------------|-------------------------|-------------------|-----------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult) |

<a id="opIdgetMultiContractKline"></a>

## GET Query Multi-Contract Quantitative K-Line

GET /api/v1/public/quote/getMultiContractKline

### Request Parameters

| Name                       | Location | Type   | Required | Description                             |
|----------------------------|----------|--------|----------|-----------------------------------------|
| contractIdList             | query    | string | No       | Collection of Contract IDs              |
| priceType                  | query    | string | No       | Price type                             |
| klineType                  | query    | string | No       | K-line type                            |
| size                       | query    | string | No       | Number to retrieve. Must be greater than 0 and less than or equal to 200 |
| filterBeginKlineTimeInclusive | query    | string | No       | Query start time (if 0, means from current time). Returns in descending order by time |
| filterEndKlineTimeExclusive   | query    | string | No       | Query end time                           |

> Response Example

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

### Response

| Status Code | Status Code Meaning     | Description       | Data Model |
|-------------|-------------------------|-------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | Inline |

### Response Data Structure

<a id="opIdgetKline"></a>

## GET Query K-Line

GET /api/v1/public/quote/getKline

### Request Parameters

| Name                       | Location | Type   | Required | Description                             |
|----------------------------|----------|--------|----------|-----------------------------------------|
| contractId                 | query    | string | No       | Contract ID                             |
| priceType                  | query    | string | No       | Price type                             |
| klineType                  | query    | string | No       | K-line type                            |
| size                       | query    | string | No       | Number to retrieve. Must be greater than 0 and less than or equal to 1000 |
| offsetData                 | query    | string | No       | Pagination offset. If empty, get the first page |
| filterBeginKlineTimeInclusive | query    | string | No       | Query start time (if 0, means from current time). Returns in descending order by time |
| filterEndKlineTimeExclusive   | query    | string | No       | Query end time                           |

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

### Response

| Status Code | Status Code Meaning     | Description       | Data Model      |
|-------------|-------------------------|-------------------|-----------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult) |

<a id="opIdgetExchangeLongShortRatio"></a>

## GET Get Exchange Long Short Ratio

GET /api/v1/public/quote/getExchangeLongShortRatio

### Request Parameters

| Name                 | Location | Type   | Required | Description                                          |
|----------------------|----------|--------|----------|------------------------------------------------------|
| range                | query    | string | No       | If empty, return data with the smallest range     |
| filterContractIdList | query    | string | No       | If empty, return data for all contracts               |
| filterExchangeList   | query    | string | No       | If empty, return data for all exchanges               |

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

### Response

| Status Code | Status Code Meaning     | Description       | Data Model      |
|-------------|-------------------------|-------------------|-----------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult) |

<a id="opIdgetDepth"></a>

## GET Query Order Book Depth

GET /api/v1/public/quote/getDepth

### Request Parameters

| Name       | Location | Type   | Required | Description                   |
|------------|----------|--------|----------|-------------------------------|
| contractId | query    | string | No       | Contract ID                   |
| level      | query    | string | No       | Depth level. Currently 15 and 200 levels available |

> Response Example

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

### Response

| Status Code | Status Code Meaning     | Description       | Data Model |
|-------------|-------------------------|-------------------|------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | Inline |

### Response Data Structure

<a id="opIdgetAccurateOpenInterest"></a>

## GET Get Accurate Open Interest

GET /api/v1/public/quote/getAccurateOpenInterest

### Request Parameters

| Name           | Location | Type   | Required | Description           |
|----------------|----------|--------|----------|-----------------------|
| contractIdList | query    | string | No       | Collection of Contract IDs |

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

### Response

| Status Code | Status Code Meaning     | Description       | Data Model      |
|-------------|-------------------------|-------------------|-----------------|
| 200         | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | default response | [Result](#schemaresult) |

# Data Models

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

### Properties

| Name        | Type                   | Required | Constraints | Chinese Name | Description                                   |
|-------------|------------------------|----------|-------------|--------------|-----------------------------------------------|
| code        | string                 | false    | none        |              | Status code. "SUCCESS" for success, others for failures  |
| data        | [[OpenInterest](#schemaopeninterest)] | false    | none        |              |  Correct response data                          |
| errorParam  | object                 | false    | none        |              | Parameter information in error messages           |
| » **additionalProperties** | string              | false    | none        |              | Parameter information in error messages |
| requestTime | string(timestamp)      | false    | none        |              | Server request reception time              |
| responseTime| string(timestamp)      | false    | none        |              | Server response return time                  |
| traceId     | string                 | false    | none        |              | Call trace ID                              |

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

Open Interest

### Properties

| Name        | Type                | Required | Constraints | Chinese Name | Description        |
|-------------|---------------------|----------|-------------|--------------|--------------------|
| contractId  | string(int64)        | false    | none        |              | Contract ID        |
| timestamp   | string              | false    | none        |              | Statistical timestamp|
| size        | string(int64)        | false    | none        |              | Open Interest      |

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

### Properties

| Name        | Type                   | Required | Constraints | Chinese Name | Description                                   |
|-------------|------------------------|----------|-------------|--------------|-----------------------------------------------|
| code        | string                 | false    | none        |              | Status code. "SUCCESS" for success, others for failures  |
| data        | [[Depth](#schemadepth)] | false    | none        |              | Correct response data                           |
| errorParam  | object                 | false    | none        |              | Parameter information in error messages           |
| » **additionalProperties** | string              | false    | none        |              | Parameter information in error messages |
| requestTime | string(timestamp)      | false    | none        |              | Server request reception time              |
| responseTime| string(timestamp)      | false    | none        |              | Server response return time                  |
| traceId     | string                 | false    | none        |              | Call trace ID                              |

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

Depth

### Properties

| Name        | Type                | Required | Constraints | Chinese Name | Description          |
|-------------|---------------------|----------|-------------|--------------|----------------------|
| startVersion | string(int64)        | false    | none        |              | Start order book version number  |
| endVersion  | string(int64)        | false    | none        |              | End order book version number   |
| level       | integer(int32)      | false    | none        |              | Depth level         |
| contractId  | string(int64)        | false    | none        |              | Contract ID          |
| contractName | string              | false    | none        |              | Contract name        |
| asks        | [[BookOrder](#schemabookorder)]| false    | none        |              | Ask list             |
| bids        | [[BookOrder](#schemabookorder)]| false    | none        |              | Bid list             |
| depthType   | string              | false    | none        |              | Depth type           |

#### Enum Values

| Property  | Value               |
|-----------|---------------------|
| depthType | UNKNOWN_DEPTH_TYPE  |
| depthType | SNAPSHOT            |
| depthType | CHANGED             |
| depthType | UNRECOGNIZED       |

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

Order Book Information

### Properties

| Name  | Type           | Required | Constraints | Chinese Name | Description |
|-------|----------------|----------|-------------|--------------|-------------|
| price | string(decimal)| false    | none        |              | Price       |
| size  | string(decimal)| false    | none        |              | Quantity    |

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

### Properties

| Name        | Type                 | Required | Constraints | Chinese Name | Description                                  |
|-------------|----------------------|----------|-------------|--------------|----------------------------------------------|
| code        | string               | false    | none        |              | Status code. "SUCCESS" for success, others for failures |
| data        | [PageDataKline](#schemapagedatakline) | false    | none        |              | Generic paginated response                       |
| errorParam  | object               | false    | none        |              | Parameter information in error messages           |
| » **additionalProperties** | string            | false    | none        |              | Parameter information in error messages |
| requestTime | string(timestamp)    | false    | none        |              | Server request reception time              |
| responseTime| string(timestamp)    | false    | none        |              | Server response return time                  |
| traceId     | string               | false    | none        |              | Call trace ID                              |

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

Generic paginated response

### Properties

| Name               | Type             | Required | Constraints | Chinese Name | Description                          |
|--------------------|------------------|----------|-------------|--------------|--------------------------------------|
| dataList           | [[Kline](#schemakline)]| false    | none        |              | Data list                            |
| nextPageOffsetData | string           | false    | none        |              | Offset for the next page. If there is no next page, it's an empty string |

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

K-Line

### Properties

| Name        | Type                | Required | Constraints | Chinese Name | Description            |
|-------------|---------------------|----------|-------------|--------------|------------------------|
| klineId     | string(int64)        | false    | none        |              | K-Line ID              |
| contractId  | string(int64)        | false    | none        |              | Perpetual contract ID  |
| contractName | string              | false    | none        |              | Perpetual contract name |
| klineType   | string              | false    | none        |              | K-Line type            |
| klineTime   | string(int64)        | false    | none        |              | K-Line time            |
| priceType   | string              | false    | none        |              | Price type of the K-line    |
| trades      | string(int64)        | false    | none        |              | Number of trades        |
| size        | string(decimal)      | false    | none        |              | Volume                 |
| value       | string(decimal)      | false    | none        |              | Value                  |
| high        | string(decimal)      | false    | none        |              | High price              |
| low         | string(decimal)      | false    | none        |              | Low price               |
| open        | string(decimal)      | false    | none        |              | Opening price          |
| close       | string(decimal)      | false    | none        |              | Closing price          |
| makerBuySize| string(decimal)     | false    | none        |              | Maker buy volume |
| makerBuyValue | string(decimal)     | false    | none        |              | Maker buy value |

#### Enum Values

| Property  | Value              |
|-----------|--------------------|
| klineType | UNKNOWN_KLINE_TYPE  |
| klineType | MINUTE_1            |
| klineType | MINUTE_5            |
| klineType | MINUTE_15           |
| klineType | MINUTE_30           |
| klineType | HOUR_1              |
| klineType | HOUR_2              |
| klineType | HOUR_4              |
| klineType | HOUR_6              |
| klineType | HOUR_8              |
| klineType | HOUR_12             |
| klineType | DAY_1               |
| klineType | WEEK_1              |
| klineType | MONTH_1             |
| klineType | UNRECOGNIZED       |
| priceType | UNKNOWN_PRICE_TYPE |
| priceType | ORACLE_PRICE       |
| priceType | INDEX_PRICE        |
| priceType | LAST_PRICE         |
| priceType | ASK1_PRICE        |
| priceType | BID1_PRICE        |
| priceType | OPEN_INTEREST        |
| priceType | UNRECOGNIZED       |

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

### Properties

| Name        | Type                  | Required | Constraints | Chinese Name | Description                                   |
|-------------|-----------------------|----------|-------------|--------------|-----------------------------------------------|
| code        | string                | false    | none        |              | Status code. "SUCCESS" for success, others for failures |
| data        | [[ContractMultiKline](#schemacontractmultikline)]| false    | none        |              | Correct response data                           |
| errorParam  | object                | false    | none        |              | Parameter information in error messages           |
| » **additionalProperties** | string             | false    | none        |              | Parameter information in error messages |
| requestTime | string(timestamp)     | false    | none        |              | Server request reception time              |
| responseTime| string(timestamp)     | false    | none        |              | Server response return time                  |
| traceId     | string                | false    | none        |              | Call trace ID                              |

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

Multiple K-Lines for a Contract

### Properties

| Name        | Type                | Required | Constraints | Chinese Name | Description               |
|-------------|---------------------|----------|-------------|--------------|---------------------------|
| contractId  | string(int64)        | false    | none        |              | Perpetual contract ID     |
| klineList   | [[Kline](#schemakline)]  | false    | none        |              | Collection of kline data |

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

### Properties

| Name        | Type                   | Required | Constraints | Chinese Name | Description                                   |
|-------------|------------------------|----------|-------------|--------------|-----------------------------------------------|
| code        | string                 | false    | none        |              | Status code. "SUCCESS" for success, others for failures  |
| data        | [[StatDayTrade](#schemastatdaytrade)]| false    | none        |              | Correct response data                           |
| errorParam  | object                 | false    | none        |              | Parameter information in error messages           |
| » **additionalProperties** | string              | false    | none        |              | Parameter information in error messages |
| requestTime | string(timestamp)      | false    | none        |              | Server request reception time              |
| responseTime| string(timestamp)      | false    | none        |              | Server response return time                  |
| traceId     | string                 | false    | none        |              | Call trace ID                              |

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

Daily Trading Information

### Properties

| Name        | Type                | Required | Constraints | Chinese Name | Description        |
|-------------|---------------------|----------|-------------|--------------|--------------------|
| dayTime     | string(int64)        | false    | none        |              | Date             |
| totalTrades | string(int64)        | false    | none        |              | Total number of trades  |
| totalValue  | string              | false    | none        |              | Total trading value   |
| createTime  | string(int64)        | false    | none        |              | Creation time     |

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
      "highTime": "```json
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

### Properties

| Name        | Type                   | Required | Constraints | Chinese Name | Description                                   |
|-------------|------------------------|----------|-------------|--------------|-----------------------------------------------|
| code        | string                 | false    | none        |              | Status code. "SUCCESS" for success, others for failures  |
| data        | [[Ticker](#schematicker)] | false    | none        |              | Correct response data                           |
| errorParam  | object                 | false    | none        |              | Parameter information in error messages           |
| » **additionalProperties** | string              | false    | none        |              | Parameter information in error messages |
| requestTime | string(timestamp)      | false    | none        |              | Server request reception time              |
| responseTime| string(timestamp)      | false    | none        |              | Server response return time                  |
| traceId     | string                 | false    | none        |              | Call trace ID                              |

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

24-Hour Quotes

### Properties

| Name            | Type           | Required | Constraints | Chinese Name | Description                    |
|-----------------|----------------|----------|-------------|--------------|--------------------------------|
| contractId      | string(int64)   | false    | none        |              | Contract ID                    |
| contractName    | string         | false    | none        |              | Contract Name                  |
| priceChange     | string(decimal) | false    | none        |              | Price change                   |
| priceChangePercent | string(decimal)| false    | none        |              | Price change percentage         |
| trades          | string(int64)   | false    | none        |              | 24-hour number of trades      |
| size            | string(decimal) | false    | none        |              | 24-hour trading volume         |
| value           | string(decimal) | false    | none        |              | 24-hour trading value          |
| high            | string(decimal) | false    | none        |              | 24-hour high price              |
| low             | string(decimal) | false    | none        |              | 24-hour low price              |
| open            | string(decimal) | false    | none        |              | 24-hour opening price          |
| close           | string(decimal) | false    | none        |              | 24-hour closing price          |
| highTime        | string(int64)   | false    | none        |              | 24-hour high price time        |
| lowTime         | string(int64)   | false    | none        |              | 24-hour low price time        |
| startTime       | string(int64)   | false    | none        |              | 24-hour quote start time       |
| endTime         | string(int64)   | false    | none        |              | 24-hour quote end time         |
| lastPrice       | string(decimal) | false    | none        |              | Latest trade price            |
| indexPrice      | string(decimal) | false    | none        |              | Current index price            |
| oraclePrice     | string(decimal) | false    | none        |              | Current oracle price         |
| openInterest    | string(decimal) | false    | none        |              | Open Interest                |
| fundingRate     | string         | false    | none        |              | Current already settled funding rate    |
| fundingTime     | string(int64)   | false    | none        |              | Funding rate settlement time   |
| nextFundingTime | string(int64)   | false    | none        |              | Next funding rate settlement time|

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

### Properties

| Name        | Type                      | Required | Constraints | Chinese Name | Description                               |
|-------------|---------------------------|----------|-------------|--------------|-------------------------------------------|
| code        | string                    | false    | none        |              | Status code. "SUCCESS" for success, others for failures |
| data        | [GetTickerSummary](#schemagettickersummary)  | false    | none        |              | Get quote summary response                |
| errorParam  | object                    | false    | none        |              | Parameter information in error messages         |
| » **additionalProperties** | string               | false    | none        |              | Parameter information in error messages|
| requestTime | string(timestamp)         | false    | none        |              | Server request reception time            |
| responseTime| string(timestamp)         | false    | none        |              | Server response return time                |
| traceId     | string                    | false    | none        |              | Call trace ID                           |

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

Get Quote Summary Response

### Properties

| Name          | Type                 | Required | Constraints | Chinese Name | Description      |
|---------------|----------------------|----------|-------------|--------------|------------------|
| tickerSummary | [TickerSummary](#schematickersummary) | false    | none        |              | Quote summary  |

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

Quote Summary

### Properties

| Name         | Type   | Required | Constraints | Chinese Name | Description              |
|--------------|--------|----------|-------------|--------------|--------------------------|
| period       | string | false    | none        |              | Summary period             |
| trades       | string | false    | none        |              | Total exchange number of trades  |
| value        | string | false    | none        |              | Total traded value         |
| openInterest | string | false    | none        |              | Current total open interest |

#### Enum Values

| Property | Value            |
|----------|------------------|
| period   | UNKNOWN_PERIOD   |
| period   | LAST_DAY_1        |
| period   | LAST_DAY_7        |
| period   | LAST_DAY_30       |
| period   | UNRECOGNIZED     |

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

Generic Response Structure

### Properties

| Name         | Type             | Required | Constraints | Chinese Name | Description                          |
|--------------|------------------|----------|-------------|--------------|--------------------------------------|
| code         | string           | false    | none        |              | Status code. "SUCCESS" for success, others for failures |
| msg          | string           | false    | none        |              | Detailed error message when an error occurs |
| requestTime  | string(int64)     | false    | none        |              | Server request reception time          |
| responseTime | string(int64)    | false    | none        |              | Server response return time              |
