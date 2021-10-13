# 🔒 Get payment data

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/payments/:paymentId" method="get" summary="Get deposit data" %}
{% swagger-description %}
Get payment details for a specific payment ID. Finrax payment ID is provided in the response of POST 

`/payments`
{% endswagger-description %}

{% swagger-parameter in="path" name="paymentId" type="uuid" required="true" %}
Unique Finrax payment ID
{% endswagger-parameter %}

{% swagger-response status="200" description="Successfully retrieved payment data" %}
```javascript
{
    "expectedUniformAmount": "13.00",
    "expectedDepositAmount": "0.08754164",
    "locale": "en-US",
    "expectedDisplayAmount": "15.00",
    "paymentInitiatedAt": 1634056128,
    "paymentRequestedAt": 1634056139,
    "actualDepositAmount": "0.08754164",
    "depositCurrency": "LTC",
    "actualDisplayAmount": "15.00",
    "expirationMinutes": 30,
    "paymentId": "4cd66dc4-1e81-4c4a-b74c-ab3d59a3febc",
    "walletAddress": "MEEnUHjjS1GjXiA8UiNMfnb9dQ4ZbyPJhY",
    "processorType": "BLOCKCHAIN",
    "displayCurrency": "USD",
    "businessId": "dab81a7a-2502-4784-ad34-87e04e5129f0",
    "deposits": [
        {
            "depositAmount": "0.08754164",
            "depositCurrency": "LTC",
            "depositReceivedAt": 1634056507,
            "displayAmount": "15.00000000",
            "displayCurrency": "USD",
            "fromAddress": "LZBRa7MJ4WZKqrigX1kW93xH4aGpNTd71U",
            "id": "ff4106d6-d6c7-31e9-8303-bbfda83c2f54",
            "onChainFee": "0.00000362",
            "refund": {
                "amount": "0.08245836",
                "confirmedAt": 1634056641,
                "displayAmount": "14.13",
                "displayCurrency": "USD",
                "displayFee": "0.17",
                "fee": "0.00100000",
                "reason": "OVERPAYMENT",
                "status": "CONFIRMED",
                "transactionId": "1f858f5c5268c9135459e21a9d711666140e31ac31304e73b591846f30fee217",
                "type": "PARTIAL"
            },
            "toAddress": "MEEnUHjjS1GjXiA8UiNMfnb9dQ4ZbyPJhY",
            "transactionId": "80d375925f268e3750b4198baf67d9ef78c649f610d286c84143bc807e628d5c"
        }
    ],
    "rateType": "FIXED",
    "status": "OVERPAID",
    "refundFollowUpDepositsForOneTimePayments": true,
    "ltc3Address": "382eAQKmUtRJjCtENqP1r9LkJhU7gksjGn",
    "type": "ONE_TIME",
    "overpaymentPolicy": "EXCESS_REFUND",
    "clientPaymentId": "testPayment"
}
```
{% endswagger-response %}
{% endswagger %}

### Response schema

| Parameter                                | Type                                                | Description                                                                                                    |
| ---------------------------------------- | --------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| actualDepositAmount                      | string <mark style="color:red;">\[required]</mark>  | Actual amount deposited in cryptocurrency by the end user                                                      |
| actualDisplayAmount                      | string <mark style="color:red;">\[required]</mark>  | Actual amount deposited in display currency `EUR,USD,GBP`                                                      |
| businessId                               | string <mark style="color:red;">\[required]</mark>  | Unique business identifier `UUID`                                                                              |
| clientPaymentId                          | string <mark style="color:red;">\[required]</mark>  | Unique payment identifier provided by the merchant in the request body of POST `/payments`                     |
| depositCurrency                          | string <mark style="color:red;">\[optional]</mark>  | The selected cryptocurrency for this payment                                                                   |
| deposits                                 | array <mark style="color:red;">\[required]</mark>   | Array with all deposits for this payment (could be multiple)                                                   |
|       depositAmount                      | string <mark style="color:red;">\[required]</mark>  | Amount deposited in cryptocurrency                                                                             |
|       depositCurrency                    | string <mark style="color:red;">\[required]</mark>  | Cryptocurrency that has been deposited                                                                         |
|       displayCurrency                    | string <mark style="color:red;">\[required]</mark>  | The fiat currency chosen for denomination purposes                                                             |
|       depositReceivedAt                  | number <mark style="color:red;">\[required]</mark>  | Timestamp when the deposit was received `UNIX`                                                                 |
|       displayAmount                      | string <mark style="color:red;">\[required]</mark>  | Amount in display currency calculated at receive time                                                          |
|       id                                 | string <mark style="color:red;">\[required]</mark>  | Unique Finrax deposit identifier `UUID`                                                                        |
|       onChainFee                         | string <mark style="color:red;">\[required]</mark>  | Blockchain cost for this deposit paid by the end user                                                          |
|       fromAddress                        | string <mark style="color:red;">\[required]</mark>  | The sending address of the transaction.                                                                        |
|       toAddress                          | string <mark style="color:red;">\[required]</mark>  | Your unique blockchain address supplied by Finrax where the deposit was received                               |
|       transactionId                      | string <mark style="color:red;">\[required]</mark>  | Unique blockchain transaction ID of the deposit                                                                |
|       refund                             | object <mark style="color:red;">\[optional]</mark>  | In case of overpayments or follow-up transactions                                                              |
|             type                         | string <mark style="color:red;">\[required]</mark>  | Could be one of: `PARTIAL` or `FULL`                                                                           |
|             status                       | string <mark style="color:red;">\[required]</mark>  | Could be one of: `PENDING` or `CONFIRMED` or `NON_REFUNDABLE`                                                  |
|             reason                       | string <mark style="color:red;">\[required]</mark>  | Could be one of: `OVERPAYMENT` or `FOLLOW_UP_DEPOSIT`                                                          |
|             amount                       | string <mark style="color:red;">\[required]</mark>  | Amount in cryptocurrency that needs to be refunded                                                             |
|             fee                          | string <mark style="color:red;">\[required]</mark>  | On-chain fee in cryptocurrency                                                                                 |
|             displayCurrency              | string <mark style="color:red;">\[required]</mark>  | The fiat currency chosen for denomination purposes                                                             |
|             displayAmount                | string <mark style="color:red;">\[required]</mark>  | Amount in fiat currency that needs to be refunded                                                              |
|             displayFee                   | string <mark style="color:red;">\[required]</mark>  | On-chain fee in displayCurrency                                                                                |
|             transactionId                | string <mark style="color:red;">\[optional]</mark>  | Unique blockchain transaction hash of the refund                                                               |
|             confirmedAt                  | number <mark style="color:red;">\[optional]</mark>  | Timestamp when the refund has been confirmed in `UNIX`                                                         |
| displayCurrency                          | string <mark style="color:red;">\[optional]</mark>  | The fiat currency chosen for denomination purposes                                                             |
| expectedDepositAmount                    | string <mark style="color:red;">\[optional]</mark>  | Amount in cryptocurrency to be deposited to fulfill the required amount in `displayCurrency`                   |
| expectedDisplayAmount                    | string <mark style="color:red;">\[optional]</mark>  | Amount in `displayCurrency `requested for this payment                                                         |
| expirationMinutes                        | number <mark style="color:red;">\[required]</mark>  | Timeframe in which the deposit should succeed                                                                  |
| locale                                   | string <mark style="color:red;">\[required]</mark>  | Language localisation abbreviation                                                                             |
| paymentId                                | string <mark style="color:red;">\[required]</mark>  | Unique Finrax payment identifier `UUID`                                                                        |
| paymentInitiatedAt                       | number <mark style="color:red;">\[required]</mark>  | Timestamp when the payment was initiated `UNIX`                                                                |
| paymentRequestedAt                       | number <mark style="color:red;">\[optional]</mark>  | Timestamp when the payment was requested `UNIX`                                                                |
| status                                   | string <mark style="color:red;">\[required]</mark>  | Defines the status of the payment. Can be one of \[NEW, PENDING, AWAITING, EXPIRED, DEPOSITED]                 |
| redirectUrl                              | string <mark style="color:red;">\[optional]</mark>  | Custom URL where the user should get redirected after payment completion.                                      |
| actualUniformAmount                      | string <mark style="color:red;">\[optional]</mark>  | Actual amount deposited in EUR                                                                                 |
| expectedUniformAmount                    | string <mark style="color:red;">\[optional]</mark>  | Expected deposit amount in EUR                                                                                 |
| destinationTag                           | string <mark style="color:red;">\[optional]</mark>  | Applicable for XRP and XLM                                                                                     |
| ltc3address                              | string <mark style="color:red;">\[optional]</mark>  | Legacy 3-prefix address for LTC                                                                                |
| refundFollowUpDepositsForOneTimePayments | boolean <mark style="color:red;">\[optional]</mark> | Payment configuration if follow-up deposits should be refunded.                                                |
| overpaymentPolicy                        | string <mark style="color:red;">\[optional]</mark>  | Payment configuration for overpayments. Can be one of: `EXCESS_REFUND` or `PROCESS`                            |
| type                                     | string <mark style="color:red;">\[required]</mark>  | Can be one of: `REUSABLE` or `ONE_TIME`                                                                        |
| rateType                                 | string <mark style="color:red;">\[required]</mark>  | Can be one of: `FIXED` or `FLOATING`                                                                           |
| walletAddress                            | string <mark style="color:red;">\[optional]</mark>  | Unique wallet address generated by Finrax for this payment where the cryptocurrency amount should be deposited |

