# Errors

### Format

For both client and server errors the API uses JSON as transport in the following format

```javascript
{
    "timestamp": 1584539613,
    "httpStatus": 400,
    "httpError": "Bad Request",
    "message": "Request failed validation",
    "path": "/api/v1/{all_endpoints}",
}
```

### HTTP Codes

| Code | Meaning | Description |
| :--- | :--- | :--- |
| 400 | Bad request | Invalid request parameters |
| 401 | Unauthorized | Invalid authorization token or API credentials |
| 403 | Forbidden | Insufficient permissions for accessing the desired resource |
| 404 | Not found | Resource doesn't exist |
| 405 | Method not allowed | The specified resource does not support the supplied HTTP verb |
| 409 | Conflict | Possible duplication of unique constraint |
| 415 | Unsupported media type | The request was not JSON-serialized |
| 500 | Internal server error | Issue with our servers. Try again later or contact us |
| 503 | Service unavailable | System is down |



