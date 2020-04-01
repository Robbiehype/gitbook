---
description: Finrax REST API authorization schema
---

# Authorization

### How does it work?

Finrax REST API uses standard HTTP Authorization header to pass authentication information. Under the  authentication scheme, this header has the following form:

```aspnet
'Authorization: FRX-API api-key=<your_api_key>,
                        signature=<signature>,
                        timestamp=<unix_timestamp>'
```

API credentials consist of an **API key** and an **API secret,** forming a pair together. The key must be passed with each request in the Authorization header’s API-Key component and the **API secret** is used for the generation of the [Signature](signature.md) component.  
The **Timestamp** component must be an integer value representing the current UNIX epoch time in milliseconds.

{% hint style="info" %}
**All signed requests are labeled with this icon 🔒**
{% endhint %}

{% hint style="warning" %}
**Existing integrators please refer to the** [**Legacy**](legacy.md) **section.**
{% endhint %}

