---
description: This is an authenticated endpoint
---

# Initiate deposit request 🔒

{% api-method method="post" host="https:/payments.finrax.com/" path="api/v1/payments" %}
{% api-method-summary %}
Initiate a deposit request 
{% endapi-method-summary %}

{% api-method-description %}
An endpoint for initiating a payment deposit request. On success the client will receive an unique payment URL for the deposit process which can be served within the `iframe` provided in the response or in a proprietary application.  
  
Alternatively you can redirect to the payment link and supply a `redirectUrl` to navigate back to your website upon payment completion. We also supply a button which the customer can use to manually redirect back on the merchant site.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
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
    "actualDepositAmount": "0",
    "actualDisplayAmount": "0",
    "businessId": "0268eba8-e240-4e83-b85e-d3c6c7bd9f20",
    "clientPaymentId": "MyFirstPayment",
    "deposits": [],
    "expirationMinutes": 30,
    "locale": "en-US",
    "paymentId": "47922fda-0ccb-4070-8d79-09751d023a67",
    "paymentInitiatedAt": 1566475846,
    "status": "NEW"
  },
  "paymentUrl": "https://payments.finrax.com/deposit/47922fda-0ccb-4070-8d79-09751d023a67?theme=LIGHT&locale=en-US"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid request body
{% endapi-method-response-example-description %}

```
{"error":"Invalid request body"}
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
| businessId | string | Finrax business ID `UUID` |
| clientPaymentId | string | Unique payment identifier provided in the request |
| deposits | array | Array with all the transactions that happened for this payment |
| expirationMinutes | number | The timeframe in which the deposit should happen |
| locale | string | Language localisation |
| paymentId | string | Unique payment identifier within Finrax system `UUID` |
| paymentInitiatedAt | number | Timestamp when the payment got created `UNIX` |
| status | string | Status of the payment |
| paymentUrl | string | A unique payment URL which could be used to serve the Finrax checkout page |
| redirectUrl | string | A specific URL the customer will be redirected to upon payment completion |



