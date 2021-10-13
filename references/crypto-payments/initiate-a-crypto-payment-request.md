---
description: This is an authenticated endpoint
---

# 🔒 Request crypto payment

{% swagger baseUrl="https://payments.finrax.com/" path="api/v1/payments" method="post" summary="Initiate a payment request " %}
{% swagger-description %}
An endpoint for initiating a crypto payment request. Upon success, a unique 

`paymentUrl`

is provided in the response which can be served within an

`iframe`

. 

\




\


Alternatively, you can redirect to the payment URL and if you have supplied a

`redirectUrl`

 in the request, we will navigate the end-user back to your website upon payment completion (when we have received a deposit against this payment request). There is also a button which the end-user can use if they wish to get redirected back sooner.
{% endswagger-description %}

{% swagger-parameter in="body" name="depositAmount" type="string" %}
Request amount in cryptocurrency that should be deposited (i.e. 0.55 BTC).
{% endswagger-parameter %}

{% swagger-parameter in="body" name="depositCurrency" type="string" %}
Cryptocurrency that should be used for the deposit. 

**Required**

 if 

`depositAmount`

 is supplied.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" %}
Can be one of [ONE_TIME, REUSABLE]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="rateType" type="string" %}
Can be one of [FIXED, FLOATING]. Defaults to FIXED when certain conditions are met. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="redirectUrl" type="string" %}
Redirect a customer back to a specific URL upon payment completion. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="businessId" type="string" %}
**UUID**

 Unique business identifier. Optional for businessToken implementation
{% endswagger-parameter %}

{% swagger-parameter in="body" name="expirationMinutes" type="integer" %}
`ONE_TIME`

 payments: Indicates the timeframe in which the deposit should happen. A value of 

`0`

 will make the payment expiry to 7 days. Defaults to 30 min.

\




`REUSABLE`

 payments: You can omit this parameter. Reusable payments are set to non-expiry.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="displayCurrency" type="string" %}
Fiat currency abbreviation (i.e. EUR, USD, GBP). 

**Required**

 if 

`depositAmount`

 is supplied.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="displayAmount" type="string" %}
Amount in 

`displayCurrency`

the user wants to deposit (i.e. 100 USD). One of 

**`depositAmount`**

 or 

**`displayAmount`**

 should be supplied.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="locale" type="string" required="true" %}
Language localisation 

`en-US, de-DE, es-ES, fr-FR`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientPaymentId" type="string" %}
Unique payment identifier for reconciliation purposes.
{% endswagger-parameter %}

{% swagger-response status="200" description="Payment initiated successfully" %}
```javascript
{
    "paymentInfo": {
        "actualDepositAmount": "0.00000000",
        "actualDisplayAmount": "0.00",
        "expirationMinutes": 30,
        "paymentId": "730ce768-441d-4cd6-81e2-65bd573097db",
        "processorType": "BLOCKCHAIN",
        "displayCurrency": "USD",
        "actualUniformAmount": "0.00",
        "locale": "en-US",
        "businessId": "dab81a7a-2502-4784-ad34-87e04e5129f0",
        "deposits": [],
        "rateType": "FIXED",
        "status": "NEW",
        "expectedDisplayAmount": "100.00",
        "type": "ONE_TIME",
        "refundFollowUpDepositsForOneTimePayments": true,
        "overpaymentPolicy": "EXCESS_REFUND",
        "paymentInitiatedAt": 1634141810,
        "clientPaymentId": "test-example-1"
    },
    "paymentUrl": "https://dev-payments.finrax.com/deposit/730ce768-441d-4cd6-81e2-65bd573097db?theme=LIGHT&locale=en-US&sessionToken=eyJhbGciOiJIUzUxMiJ9.eyJwYXltZW50SWQiOiI3MzBjZTc2OC00NDFkLTRjZDYtODFlMi02NWJkNTczMDk3ZGIiLCJvcmdhbmlzYXRpb25JZCI6ImNmMWU2N2QwLTQ2ZjYtNGEwMC04MzcwLTA5MGE1MDg3YzgwZiIsImJ1c2luZXNzSWQiOiJkYWI4MWE3YS0yNTAyLTQ3ODQtYWQzNC04N2UwNGU1MTI5ZjAiLCJpYXQiOjE2MzQxNDE4MTAsImV4cCI6MTYzNDE0NTQxMH0.jC5sxGSMlsFeSbfhBrOUIxzHpWzu5CNrYuy-jIpNF7IflFNCQ81kwYQ6X0ToiKqQKOEaqazJj3QntrJpQcgnXQ"
}
```
{% endswagger-response %}
{% endswagger %}

### Response schema

| Parameter             | Type   | Description                                                                                 |
| --------------------- | ------ | ------------------------------------------------------------------------------------------- |
| paymentInfo           | object | Object with payment details                                                                 |
| actualDepositAmount   | string | The actual deposit amount in cryptocurrency                                                 |
| actualDisplayAmount   | string | The actual display amount upon receiving the cryptocurrency                                 |
| expectedDepositAmount | string | The expected amount in Cryptocurrency                                                       |
| expectedDisplayAmount | string | The expected amount in Fiat currency                                                        |
| businessId            | string | Finrax business ID `UUID`                                                                   |
| clientPaymentId       | string | Unique payment identifier provided in the request                                           |
| deposits              | array  | Array with all the transactions that happened for this payment                              |
| expirationMinutes     | number | The timeframe in which the deposit should happen                                            |
| locale                | string | Language localisation                                                                       |
| paymentId             | string | Unique payment identifier within Finrax system `UUID`                                       |
| paymentInitiatedAt    | number | Timestamp when the payment got created `UNIX`                                               |
| status                | string | Status of the payment                                                                       |
| processorType         | string | Type of the payment. Can be one of \[BLOCKCHAIN, CARD]. For crypto payments it's BLOCKCHAIN |
| paymentUrl            | string | A unique payment URL which could be used to serve the Finrax checkout page                  |
| rateType              | string | Can be one of \[FIXED, FLOATING]                                                            |
| redirectUrl           | string | A specific URL the customer will be redirected to upon payment completion                   |
| type                  | string | Can be one of \[ONE_TIME, REUSABLE]                                                         |

{% hint style="info" %}
More information regarding FIXED/FLOATING rate types [here](https://blog.finrax.com/guides/fixed-rates)
{% endhint %}

{% hint style="info" %}
More information on ONE_TIME/REUSABLE payment links [here](https://blog.finrax.com/guides/one-time-payments-vs.-recurring-payments)
{% endhint %}
