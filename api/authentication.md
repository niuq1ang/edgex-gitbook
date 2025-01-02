# Authentication


## Public API

```text
No authentication is required for public interfaces.
```


## Private API
### Auth Header

| Name               | Location | Type    | Required | Description              |
| ------------------ | -------- | ------- | -------- | ------------------------ |
| `X-edgeX-Api-Timestamp` | header   | string  | must     | None                     |
| `X-edgeX-Api-Signature` | header   | string  | must     | None                     |


### Signature Elements

| **Signature Element**                  | **Description**                                                                 |
|----------------------------------------|---------------------------------------------------------------------------------|
| `X-edgeX-Api-Timestamp`                | The timestamp when the request was made. This is retrieved from the request header. |
| **Request Method (Uppercase)**         | The HTTP method of the request, converted to uppercase (e.g., GET, POST).        |
| **Request Path**                       | The URI path of the request (e.g., `/api/v1/resource`).                          |
| **Request Parameter/Body**             | The query parameters or request body, sorted alphabetically.                     |

#### Request Parameter To Signature Content

The request parameters are concatenated into a single string that forms the signature content. This string includes the timestamp, HTTP method, request path, and sorted query parameters or request body, ensuring the integrity and authenticity of the request.

For example, the following request parameters are concatenated into a single string:

>1735542383256GET/api/v1/private/account/getPositionTransactionPageaccountId=543429922991899150&filterTypeList=SETTLE_FUNDING_FEE&size=10


#### Request Body To Body String Code Example

```java
    private static final String EMPTY_STRING = "";

    private static String getValue(JsonElement valueJson) {
        if (valueJson.isJsonNull()) {
            return EMPTY_STRING;
        } else if (valueJson.isJsonPrimitive()) {
            return valueJson.getAsString();
        } else if (valueJson.isJsonArray()) {
            JsonArray valueArray = valueJson.getAsJsonArray();
            if (valueArray.isEmpty()) {
                return EMPTY_STRING;
            }
            List<String> values = new ArrayList<>();
            for (JsonElement itemValue : valueArray) {
                values.add(getValue(itemValue));
            }
            return Joiner.on("&").join(values);
        } else if (valueJson.isJsonObject()) {
            TreeMap<String, String> sortedDataMap = new TreeMap<>();
            JsonObject valueJsonObj = valueJson.getAsJsonObject();
            for (String key : valueJsonObj.keySet()) {
                sortedDataMap.put(key, getValue(valueJsonObj.get(key)));
            }
            return sortedDataMap.keySet().stream()
                    .map(key -> key + "=" + sortedDataMap.get(key))
                    .collect(Collectors.joining("&"));
        }
        return EMPTY_STRING;
    }
```

### Signature Algorithm
See the [Sign](sign.md) page for more information on the signature algorithm.