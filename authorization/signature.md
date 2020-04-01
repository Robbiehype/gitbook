---
description: How to generate the authorization signature?
---

# Signature

The Signature component of the Authorization header is a **HMAC-SHA256** digest of the elements described below  


| Element | Description |
| :--- | :--- |
| Request URI | Everything after the base URL, including query parameters if present. |
| Timestamp | UNIX epoch time in milliseconds |
| Request body | A **JSON**-serialized string of the request body. If a body is not required \(e.g. request is of type GET\) assign an empty string "" |

