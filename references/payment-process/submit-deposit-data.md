---
description: >-
  If you are using our payment URL supplied as a response of Initiate deposit
  request you'll not need to run this request. It will be handled by our hosted
  checkout application.
---

# Submit deposit data 🔒

![](../../.gitbook/assets/component-81.png)

{% api-method method="patch" host="https://payments.finrax.com" path="/api/v1/payments/:paymentId" %}
{% api-method-summary %}
Submit deposit data
{% endapi-method-summary %}

{% api-method-description %}
In case you'd like to spin off your own UI, this endpoint allows you to submit the details from the end-user for the initiated deposit request. The end-user will be required to choose a `depositCurrency` i.e. the cryptocurrency they want to deposit in. Once the request is submitted, the end-user will be supplied with a `walletAddress` and the `expectedDepositAmount` calculated using the most recent exchange rate.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="paymentId" type="number" required=true %}
Unique payment identifier provided as a response of POST `/payments`
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="depositCurrency" type="string" required=true %}
Cryptocurrency that should be used for the deposit
{% endapi-method-parameter %}

{% api-method-parameter name="displayCurrency" type="string" required=false %}
Fiat currency code, if not supplied in POST `/payments` 
{% endapi-method-parameter %}

{% api-method-parameter name="displayAmount" type="number" required=false %}
Amount in display currency the user wants to deposit, if not supplied in POST`/payments` 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Payment data submitted successfully
{% endapi-method-response-example-description %}

```javascript
{
  "paymentInfo": {
    "actualDepositAmount": "0",
    "actualDisplayAmount": "0",
    "businessId": "0268eba8-e240-4e83-b85e-d3c6c7bd9f20",
    "clientPaymentId": "DepositForUserX",
    "depositCurrency": "BTC",
    "deposits": [],
    "displayCurrency": "USD",
    "expectedDepositAmount": "0.00976816",
    "expectedDisplayAmount": "100.00",
    "expirationMinutes": 30,
    "locale": "en-US",
    "paymentId": "50f0bfb3-c23e-4518-ad8f-c813a32f4822",
    "paymentInitiatedAt": 1566543952,
    "paymentRequestedAt": 1566544011,
    "status": "PENDING",
    "walletAddress": "34m1CQ5yqyvtqsoNH2zKAwLw7GCFz8FJQA"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Response schema

| Parameter | Type | Description |
| :--- | :--- | :--- |
| paymentInfo | object | Contains all payment relevant data |
| actualDepositAmount | string | Actual amount deposited in cryptocurrency  |
| actualDisplayAmount | string | Actual amount deposited in display currency |
| businessId | string | Unique business identifier `UUID` |
| clientPaymentId | string | Unique payment identifier provided in the request body of POST `/payments` |
| depositCurrency | string | The selected cryptocurrency for this payment |
| deposits | array | Array with all transactions for this payment |
| displayCurrency | string | The fiat currency chosen for display purposes |
| expectedDepositAmount | string | Amount in cryptocurrency to be deposited to fulfill the required amount in `displayCurrency` |
| expectedDisplayAmount | string | Amount in `displayCurrency` requested for this payment |
| expirationMinutes | number | Timeframe in which the deposit should succeed |
| locale | string | Language localisation abbreviation  |
| paymentId | string | Unique Finrax payment identifier `UUID` |
| paymentInitiatedAt | number | Timestamp when the payment was initiated `UNIX` |
| paymentRequestedAt | number | Timestamp when the payment was requested `UNIX` |
| status | string | Defines the status of the payment |
| walletAddress | string | Unique wallet address generated by Finrax for this payment where the cryptocurrency amount should be deposited |



