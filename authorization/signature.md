---
description: How to generate the authorization signature
---

# Signature

The Signature component of the Authorization header is an **HMAC-SHA256** digest of the elements described below  


| Element | Description |
| :--- | :--- |
| Request URI | Everything after the base URL, including query parameters if present. |
| Timestamp | Current [UNIX epoch time ](https://www.unixtimestamp.com/)in milliseconds |
| Request body | A ****[minified ](https://codebeautify.org/jsonminifier)**JSON**-serialized string of the request body. If a body is not required \(e.g. request is of type GET\), use an empty string. |

