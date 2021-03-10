---
description: This is an authenticated endpoint
---

# 🔒 Request crypto payment

{% api-method method="post" host="https://payments.finrax.com/" path="api/v1/payments" %}
{% api-method-summary %}
Initiate a payment request 
{% endapi-method-summary %}

{% api-method-description %}
An endpoint for initiating a crypto payment request. Upon success, a unique `paymentUrl`is provided in the response which can be served within an`iframe`.   
  
Alternatively, you can redirect to the payment URL and if you have supplied a`redirectUrl` in the request, we will navigate the end-user back to your website upon payment completion \(when we have received a deposit against this payment request\). There is also a button which the end-user can use if they wish to get redirected back sooner.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="type" type="string" required=false %}
Can be one of \[ONE\_TIME, REUSABLE\]
{% endapi-method-parameter %}

{% api-method-parameter name="rateType" type="string" required=false %}
Can be one of \[FIXED, FLOATING\]. Defaults to FIXED when certain conditions are met. 
{% endapi-method-parameter %}

{% api-method-parameter name="redirectUrl" type="string" required=false %}
Redirect a customer back to a specific URL upon payment completion. 
{% endapi-method-parameter %}

{% api-method-parameter name="businessId" type="string" required=true %}
**UUID** Unique business identifier. Optional for businessToken implementation
{% endapi-method-parameter %}

{% api-method-parameter name="expirationMinutes" type="number" required=false %}
Indicates the timeframe in which the deposit should happen. A value of `0` will make the payment to not expire. Defaults to `30min`
{% endapi-method-parameter %}

{% api-method-parameter name="displayCurrency" type="string" required=false %}
Fiat currency code that is supported in the business  
`EUR, USD, TRY, GBP, etc.`
{% endapi-method-parameter %}

{% api-method-parameter name="displayAmount" type="number" required=false %}
Amount in `displayCurrency`the user wants to deposit.
{% endapi-method-parameter %}

{% api-method-parameter name="locale" type="string" required=true %}
Language localisation `en-US, de-DE, es-ES, fr-FR`
{% endapi-method-parameter %}

{% api-method-parameter name="clientPaymentId" type="string" required=true %}
Unique payment identifier for reconciliation purposes.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Payment initiated successfully
{% endapi-method-response-example-description %}

```javascript
{
    "paymentInfo": {
        "paymentRequestedAt": null,
        "actualDepositAmount": "0",
        "redirectUrl": null,
        "depositCurrency": null,
        "actualDisplayAmount": "0",
        "expirationMinutes": 30,
        "paymentId": "25821749-f2d7-4189-9164-2e8018bbd85c",
        "expectedUniformAmount": null,
        "expectedDepositAmount": null,
        "walletAddress": null,
        "processorType": "BLOCKCHAIN",
        "displayCurrency": "USD",
        "actualUniformAmount": "0",
        "locale": "en-US",
        "businessId": "19dee3c4-4dc9-4bcc-b8ed-91e3d4f256bd",
        "deposits": [],
        "rateType": "FIXED",
        "status": "NEW",
        "expectedDisplayAmount": "100.00",
        "destinationTag": null,
        "ltc3Address": null,
        "type": "ONE_TIME",
        "paymentInitiatedAt": 1615384075,
        "clientPaymentId": "test-example-1"
    },
    "paymentUrl": "https://dev-payments.finrax.com/deposit/25851749-f2d7-4189-9164-2e8018bbd85c?theme=LIGHT&locale=en-US&sessionToken=eyJhbGciOiJIUzUxMiJ9.eyJwYXltZW50SWQiOiIyNTg1MTc0OS1mMmQ3LTQxODktOTE2NC0yZTgwMThiYmQ4NWMiLCJvcmdhbmlzYXRpb25JZCI6ImNmMWU2N2QwLTQ2ZjYtNGEwMC04MzcwLTA5MGE1MDg3YzgwZiIsImJ1c2luZXNzSWQiOiIxOWRlZTNjNC00ZGM5LTRiY2MtYjhlZC05MmUzZDRmMjU2YmQiLCJpYXQiOjE2MTUzODQwNzUsImV4cCI6MTYxNTM4NzY3NX0.nx3fxBR1SDhrqEEroN4ACcHlPhjMreSh9ucEPRCB4fXS4X3pO8PNkdcIvoL6g_uThEBzCU_jT8w8tr0O9pSwig"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Response schema

| Parameter | Type | Description |
| :--- | :--- | :--- |
| paymentInfo | object | Object with payment details |
| actualDepositAmount | string | The actual deposit amount in cryptocurrency |
| actualDisplayAmount | string | The actual display amount upon receiving the cryptocurrency |
| expectedDepositAmount | string | The expected amount in Cryptocurrency |
| expectedDisplayAmount | string | The expected amount in Fiat currency |
| businessId | string | Finrax business ID `UUID` |
| clientPaymentId | string | Unique payment identifier provided in the request |
| deposits | array | Array with all the transactions that happened for this payment |
| expirationMinutes | number | The timeframe in which the deposit should happen |
| locale | string | Language localisation |
| paymentId | string | Unique payment identifier within Finrax system `UUID` |
| paymentInitiatedAt | number | Timestamp when the payment got created `UNIX` |
| status | string | Status of the payment |
| processorType | string | Type of the payment. Can be one of \[BLOCKCHAIN, CARD\]. For crypto payments it's BLOCKCHAIN |
| paymentUrl | string | A unique payment URL which could be used to serve the Finrax checkout page |
| rateType | string | Can be one of \[FIXED, FLOATING\] |
| redirectUrl | string | A specific URL the customer will be redirected to upon payment completion |
| type | string | Can be one of \[ONE\_TIME, REUSABLE\] |



