---
description: The Finrax API's authorization scheme
---

# Authorization

When authorizing against the Finrax REST API, one must provide a standard HTTP `Authorization `header in the following format:

```aspnet
'Authorization: FRX-API api-key=<your_api_key>,
                        signature=<signature>,
                        timestamp=<unix_timestamp>'
```

[API credentials](management.md) consist of an **API key** and an **API secret,** forming a pair together. The key must be passed with each request in the Authorization header’s API-Key component and the **API secret** is used for the generation of the [Signature](signature.md) component.\
The **Timestamp** component must be an integer value representing the current [UNIX epoch time](https://www.unixtimestamp.com) in milliseconds.

{% hint style="info" %}
**All requests that require authorization are labelled with this icon 🔒**
{% endhint %}

{% hint style="warning" %}
**API consumers that still rely on the legacy business tokens, please refer to **[**this section**](legacy.md)**.**
{% endhint %}
