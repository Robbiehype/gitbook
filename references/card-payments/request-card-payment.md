# 🔒 Request card payment



{% api-method method="post" host="https://payments.finrax.com/" path="api/v1/payments/fiat" %}
{% api-method-summary %}
Initiate a deposit request
{% endapi-method-summary %}

{% api-method-description %}
An endpoint for initiating a fiat card payment request. Upon success, a unique `paymentUrl` is provided in the response which can be served within an `iframe`  
  
Alternatively, you can redirect to the payment URL and if you have supplied a`redirectUrl`in the request, we will navigate the end-user back to your website upon payment completion \(when we have received a deposit against this payment request\).
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="address" type="object" required=false %}
A nested optional object containing the address information of the payer. The fields of this object are described below:
{% endapi-method-parameter %}

{% api-method-parameter name="address.state" type="string" required=false %}
If the country is the USA, an optional US state can be provided
{% endapi-method-parameter %}

{% api-method-parameter name="address.country" type="string" required=true %}
Country of the payer.
{% endapi-method-parameter %}

{% api-method-parameter name="payerEmail" type="string" required=true %}
The e-mail of the payer
{% endapi-method-parameter %}

{% api-method-parameter name="displayAmount" type="string" required=true %}
Amount in displayCurrencythe user wants to deposit
{% endapi-method-parameter %}

{% api-method-parameter name="displayCurrency" type="string" required=true %}
Fiat currency code that is supported in the business EUR, USD, GBP, etc
{% endapi-method-parameter %}

{% api-method-parameter name="businessId" type="string" required=true %}
Unique Finrax Business UUID identifier.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "paymentInfo": {
        "actualDepositAmount": "0",
        "actualDisplayAmount": "0",
        "businessId": "c1fb0588-6267-4153-ae3f-8b031c66c0d0",
        "clientPaymentId": "example-payment-id",
        "depositCurrency": "BTC",
        "deposits": [],
        "displayCurrency": "EUR",
        "expectedDisplayAmount": "60.00",
        "expirationMinutes": 10080,
        "isSuspicious": false,
        "locale": "en-US",
        "paymentId": "336dc75a-17cf-4999-a1a7-9b8d37216e42",
        "paymentInitiatedAt": 1603824916,
        "processorType": "CARD",
        "status": "PENDING",
        "type": "ONE_TIME",
        "walletAddress": "3F6UF5kuoVawX6sof8KitnCEkYCMKDsR53"
    },
    "paymentUrl": "https://deposits.finrax.com/fiat/336dc75a-17cf-4999-a1a7-9b8d37216e42?amount=56.87203791469194312796208530805687&address=3F6UF5kuoVawX6sof8KitnCEkYCMKDsR53&addressSignature=0b6dfa04dfb16dbe21f30a210658cbae2f37d046cd84998d134f402c6079deca&sessionToken=eyJhbGciOiJIUzUxMiJ9.eyJwYXltZW50SWQiOiIzMzZkYzc1YS0xN2NmLTQ5OTktYTFhNy05YjhkMzcyMTZlNDIiLCJvcmdhbmlzYXRpb25JZCI6Ijg2Y2Q5MGEzLWZmOWItNDVhNy1iZTJhLTZjOGIzYjRhYzFjMCIsImJ1c2luZXNzSWQiOiJhMWZiMDU4OC02MjY3LTQxNTMtYWUzZi04YjAzMWM2NmMwZjAiLCJpYXQiOjE2MDM4MjQ5MTYsInBheWVyRW1haWwiOiJpdmF5bG9AZmlucmF4LmNvbSIsImV4cCI6MTYwNDQzMTUxNn0.E3dP4MD9RlbJZO8zdPzSBlk2SSq1VnNMQD0RbWn9vLrGoQ7bhzUyx8FckTCm0Bl37Ol-yLd6QeBmA2cKxc4-Eg&depositCurrency=BTC&displayCurrency=EUR&refreshToken=%2B7%2Fl%2F%2Fo8qE2aFJLLWLt%2BDVKeZ9%2Fl5vMVryzJHoE3iL7xOqtsZ8x%2BcpVqnwGG4U1M"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Response Schema

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
| processorType | string | Type of the payment. Can be one of \[BLOCKCHAIN, CARD\]. For crypto payments it's BLOCKCHAIN |
| paymentUrl | string | A unique payment URL which could be used to serve the Finrax checkout page |
| redirectUrl | string | A specific URL the customer will be redirected to upon payment completion |
| type | string | Can be one of \[ONE\_TIME, REUSABLE\] |
| walletAddress | string | Crypto wallet address that is going to be used as an intermediary address to complete the payment flow |
| depositCurrency | string | The cryptocurrency used as an intermediary |
| displayCurrency | string | The selected fiat currency for this payment  |



