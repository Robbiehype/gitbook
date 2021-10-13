---
description: >-
  If you are using our payment URL supplied as a response of Initiate deposit
  request you'll not need to run this request. It will be handled by our hosted
  checkout application.
---

# 🔒 Add payment details

![](<../../.gitbook/assets/Component 81.png>)

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/payments/:paymentId" method="patch" summary="Submit deposit data" %}
{% swagger-description %}
In case you'd like to spin off your own UI, this endpoint allows you to submit the details from the end-user for the initiated deposit request. The end-user will be required to choose a 

`depositCurrency`

 i.e. the cryptocurrency they want to deposit in. Once the request is submitted, the end-user will be supplied with a 

`walletAddress`

 and the 

`expectedDepositAmount`

 calculated using the most recent exchange rate.
{% endswagger-description %}

{% swagger-parameter in="path" name="paymentId" type="number" %}
Unique payment identifier provided as a response of POST 

`/payments`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="depositCurrency" type="string" %}
Cryptocurrency that should be used for the deposit
{% endswagger-parameter %}

{% swagger-parameter in="body" name="displayCurrency" type="string" %}
Fiat currency code, if not supplied in POST 

`/payments`

 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="displayAmount" type="number" %}
Amount in display currency the user wants to deposit, if not supplied in POST

`/payments`

 
{% endswagger-parameter %}

{% swagger-response status="200" description="Payment data submitted successfully" %}
```javascript
{
    "paymentInfo": {
        "expectedUniformAmount": "100.00",
        "expectedDepositAmount": "0.00205966",
        "actualUniformAmount": "0.00",
        "locale": "en-US",
        "expectedDisplayAmount": "100.00",
        "paymentInitiatedAt": 1634142279,
        "paymentRequestedAt": 1634142316,
        "actualDepositAmount": "0.00000000",
        "depositCurrency": "BTC",
        "actualDisplayAmount": "0.00",
        "expirationMinutes": 30,
        "paymentId": "5f6a3367-37b3-42cd-a870-8c74476961ac",
        "walletAddress": "33nntiQTBoM9hKZtKiWCb2NHYQuPQYa9cr",
        "processorType": "BLOCKCHAIN",
        "displayCurrency": "EUR",
        "businessId": "dab81a7a-2502-4784-ad34-87e04e5129f0",
        "deposits": [],
        "rateType": "FLOATING",
        "status": "PENDING",
        "refundFollowUpDepositsForOneTimePayments": true,
        "type": "ONE_TIME",
        "overpaymentPolicy": "EXCESS_REFUND",
        "clientPaymentId": "test_payment_1"
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Response schema

| Parameter             | Type   | Description                                                                                                    |
| --------------------- | ------ | -------------------------------------------------------------------------------------------------------------- |
| paymentInfo           | object | Contains all payment relevant data                                                                             |
| actualDepositAmount   | string | Actual amount deposited in cryptocurrency                                                                      |
| actualDisplayAmount   | string | Actual amount deposited in display currency                                                                    |
| businessId            | string | Unique business identifier `UUID`                                                                              |
| clientPaymentId       | string | Unique payment identifier provided in the request body of POST `/payments`                                     |
| depositCurrency       | string | The selected cryptocurrency for this payment                                                                   |
| deposits              | array  | Array with all transactions for this payment                                                                   |
| displayCurrency       | string | The fiat currency chosen for display purposes                                                                  |
| expectedDepositAmount | string | Amount in cryptocurrency to be deposited to fulfill the required amount in `displayCurrency`                   |
| expectedDisplayAmount | string | Amount in `displayCurrency `requested for this payment                                                         |
| expirationMinutes     | number | Timeframe in which the deposit should succeed                                                                  |
| locale                | string | Language localisation abbreviation                                                                             |
| paymentId             | string | Unique Finrax payment identifier `UUID`                                                                        |
| paymentInitiatedAt    | number | Timestamp when the payment was initiated `UNIX`                                                                |
| paymentRequestedAt    | number | Timestamp when the payment was requested `UNIX`                                                                |
| status                | string | Defines the status of the payment                                                                              |
| walletAddress         | string | Unique wallet address generated by Finrax for this payment where the cryptocurrency amount should be deposited |

