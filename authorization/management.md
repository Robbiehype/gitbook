---
description: 'How to create, edit and update API secret/key pairs'
---

# API Keys Management

API credentials can be managed directly from the [Finrax Dashboard](https://dashboard.finrax.com) by users with the [Manager or Admin roles](https://blog.finrax.com/guides/user-roles-and-permissions). To create API credentials go to **"Settings -&gt; API keys"** and click on the **“New Key”** button. Here you can provide a name \(alias\) for the key/secret pair and select the permissions that are relevant to your use-case.  
  
Due to security concerns, we also require IPs to be whitelisted. If we receive a request from an IP that was not listed for the API pair, we will reject it returning a 403 \(Forbidden\) HTTP status code.  


![](../.gitbook/assets/api-keys-creation.gif)

Upon successful API credentials creation, you will be provided with the values for the **API key** and **API secret**. At this stage, you **must store the API secret securely**, e.g. by writing it down or copying it in a trusted store as this is the only time the API secret will be displayed.   
  
Once created the API key and secret are immutable, however, the IP white-list and permissions can be edited at any time.  


{% hint style="danger" %}
**If you lose your API secret or it becomes compromised you must delete the API credentials pair immediately and generate a new one. If you find out that the access to the dashboard has been compromised, please contact us immediately.**
{% endhint %}



