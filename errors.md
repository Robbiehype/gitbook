# Errors

### Format

Both client and server errors are returned in the following format:

```javascript
{
    "timestamp": 1584539613,
    "httpStatus": 400,
    "httpError": "Bad Request",
    "message": "Request failed validation",
    "path": "/api/v1/path/to/resource",
}
```

### HTTP Status Codes

| Code | Meaning                | Description                                                   |
| ---- | ---------------------- | ------------------------------------------------------------- |
| 400  | Bad request            | Invalid request body or parameters                            |
| 401  | Unauthorized           | Invalid authorization token or API credentials                |
| 403  | Forbidden              | Insufficient permissions when accessing the resource          |
| 404  | Not found              | The requested resource doesn't exist                          |
| 405  | Method not allowed     | The endpoint does not support the supplied HTTP verb (method) |
| 409  | Conflict               | The resource cannot be created since it already exists        |
| 415  | Unsupported media type | The request's payload is not in the supported JSON format     |
| 500  | Internal server error  | There is an issue with handling the request                   |
| 503  | Service unavailable    | System is down                                                |

