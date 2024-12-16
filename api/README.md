# User Authentication

## Domain

```text
https://pro.edgex.exchange
```

## Private API Auth Header

| Name               | Location | Type    | Required | Description              |
| ------------------ | -------- | ------- | -------- | ------------------------ |
| x-edgex-api-key    | header   | string  | must     | None                     |
| x-edgex-passphrase | header   | string  | must     | None                     |
| x-edgex-signature  | header   | string  | must     | None                     |
| x-edgex-timestamp  | header   | number  | must     | None                     |

> Login to [Edgex](https://pro.edgex.exchange/trade/BTCUSDT), copy the 4 request headers, and **Request The Administrator** to configure the user list to access the API interface.

## Public API

```text
No authentication is required for public interfaces.
```
