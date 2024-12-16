# User Authentication


## Domain
```text
https://pro.edgex.exchange
```

## Private API Auth Header

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|x-edgex-api-key|header|string|must|none|
|x-edgex-passphrase|header|string|must|none|
|x-edgex-signature|header|string|must|none|
|x-edgex-timestamp|header|number|must|none|

> Login to [Edgex](https://pro.edgex.exchange/trade/BTCUSDT) cody 4 request header and <strong>Request The Administrator</strong> to configure the user list to access the API interface.

## Public API 

```text
No authentication is required for public interfaces
```