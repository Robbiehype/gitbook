# 🔒 Get business deposits

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/businesses/:id/payments" method="get" summary="Get business deposits" %}
{% swagger-description %}
Allows you to get all deposits per business ID
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the business
{% endswagger-parameter %}

{% swagger-parameter in="query" name="coins" type="array" %}
List of coins comma delimited  

`(BTC,ETH,XRP,...)`
{% endswagger-parameter %}

{% swagger-parameter in="query" name="statuses" type="string" %}
Accepts the following

\




`NEW`

 

`PENDING`

  

`DEPOSITED`

  

`AWAITING`

  

`EXPIRED`
{% endswagger-parameter %}

{% swagger-parameter in="query" name="paymentId" type="string" %}
Unique payment identifier 

`UUID`
{% endswagger-parameter %}

{% swagger-parameter in="query" name="clientPaymentId" type="string" %}
Payment ID provided by the client
{% endswagger-parameter %}

{% swagger-parameter in="query" name="descending" type="boolean" %}
Sort results in descending order
{% endswagger-parameter %}

{% swagger-parameter in="query" name="before" type="number" %}
End date of the report 

`UNIX`
{% endswagger-parameter %}

{% swagger-parameter in="query" name="after" type="number" %}
Start date of the report 

`UNIX`
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sortBy" type="string" %}
Sort payments by 

`status, created `
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="integer" %}
Limit of the results per request (max 2000)
{% endswagger-parameter %}

{% swagger-response status="200" description="Deposits fetched successfully" %}
```javascript
{
    "payments": [
        {
            "paymentRequestedAt": 1613829422,
            "actualDepositAmount": "0.00031876",
            "redirectUrl": null,
            "depositCurrency": "BTC",
            "actualDisplayAmount": "15.00000000",
            "expirationMinutes": 30,
            "paymentId": "f72c452b-16e2-44ca-957e-884d6428858d",
            "expectedUniformAmount": "15.00",
            "expectedDepositAmount": "0.00031876",
            "walletAddress": "35MQYqhKPUXVqGRrhW54o6wUKqhz1JLpyo",
            "processorType": "BLOCKCHAIN",
            "displayCurrency": "EUR",
            "actualUniformAmount": "15.00",
            "locale": "en-US",
            "businessId": "19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd",
            "deposits": [
                {
                    "depositAmount": "0.00031876",
                    "depositCurrency": "BTC",
                    "depositReceivedAt": 1613829769,
                    "displayAmount": "15.00000000",
                    "displayCurrency": "EUR",
                    "displayPayableAmount": "14.92000000",
                    "displayServiceFee": "0.08000000",
                    "id": "38d5decb-48aa-3d61-80f2-a0e57907845d",
                    "onChainFee": "0.00409298",
                    "settlementCurrency": "USDT",
                    "settlementPayableAmount": "18.09627640",
                    "settlementServiceFee": "0.09093606",
                    "toAddress": "35MQYqhKPUXVqGRrhW54o6wUKqhz1JLpyo",
                    "transactionId": "98969ddd9fb6dd445cdf7f8a7569e76b4f6441d6fa3d3efe9973e4fb967e3bdc",
                    "uniformCurrency": "EUR",
                    "uniformPayableAmount": "14.92",
                    "uniformServiceFee": "0.08"
                }
            ],
            "rateType": "FIXED",
            "status": "DEPOSITED",
            "expectedDisplayAmount": "15.00",
            "destinationTag": null,
            "ltc3Address": null,
            "type": "ONE_TIME",
            "paymentInitiatedAt": 1613829411,
            "clientPaymentId": "payment-example-id"
        },
        {
            "paymentRequestedAt": 1613551527,
            "actualDepositAmount": "0.00029343",
            "redirectUrl": null,
            "depositCurrency": "BTC",
            "actualDisplayAmount": "15.02000000",
            "expirationMinutes": 30,
            "paymentId": "373f0160-2a08-40e6-acf9-082c44147903",
            "expectedUniformAmount": "12.35",
            "expectedDepositAmount": "0.00029343",
            "walletAddress": "3AyeKf6yfFVr9y8rtJr3oW9SkVGhkLSRiZ",
            "processorType": "BLOCKCHAIN",
            "displayCurrency": "USD",
            "actualUniformAmount": "12.37",
            "locale": "en-US",
            "businessId": "19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd",
            "deposits": [
                {
                    "depositAmount": "0.00029343",
                    "depositCurrency": "BTC",
                    "depositReceivedAt": 1613551609,
                    "displayAmount": "15.02000000",
                    "displayCurrency": "USD",
                    "displayPayableAmount": "14.93000000",
                    "displayServiceFee": "0.09000000",
                    "id": "84a3a9b2-7307-305f-88fe-4c4d72ca2f30",
                    "onChainFee": "0.00191648",
                    "settlementCurrency": "USDT",
                    "settlementPayableAmount": "14.82986923",
                    "settlementServiceFee": "0.08501484",
                    "toAddress": "3AyeKf6yfFVr9y8rtJr3oW9SkVGhkLSRiZ",
                    "transactionId": "b79f3c17f1698895571af5edba47e211f388b59d41499c8e342ad8f3bc15e84e",
                    "uniformCurrency": "EUR",
                    "uniformPayableAmount": "12.30",
                    "uniformServiceFee": "0.07"
                }
            ],
            "rateType": "FLOATING",
            "status": "DEPOSITED",
            "expectedDisplayAmount": "15.00",
            "destinationTag": null,
            "ltc3Address": null,
            "type": "ONE_TIME",
            "paymentInitiatedAt": 1613551520,
            "clientPaymentId": "payment-example-2"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

#### Example: Fetch payments filtered by status DEPOSITED and coin BTC

{% tabs %}
{% tab title="Request" %}
```javascript
curl --location --request GET 'https://payments.finrax.com/api/v1/businesses/{businessId}/payments?coins=BTC&statuses=DEPOSITED' \
--header 'Content-Type: application/json' \
--header 'Authorization: FRX-API api-key=<your_api_key>,signature=<your_signature>,timestamp=<current_timestamp>'
```
{% endtab %}

{% tab title="Response" %}
```javascript
{
    "payments": [
        {
            "expectedUniformAmount": "13.00",
            "expectedDepositAmount": "0.08754164",
            "actualUniformAmount": "13.00",
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
                    "displayPayableAmount": "14.85000000",
                    "displayServiceFee": "0.15000000",
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
                    "riskScore": "0.08",
                    "settlementCurrency": "USDT",
                    "settlementPayableAmount": "14.83837684",
                    "settlementServiceFee": "0.14988259",
                    "toAddress": "MEEnUHjjS1GjXiA8UiNMfnb9dQ4ZbyPJhY",
                    "transactionId": "80d375925f268e3750b4198baf67d9ef78c649f610d286c84143bc807e628d5c",
                    "uniformCurrency": "EUR",
                    "uniformPayableAmount": "12.87",
                    "uniformServiceFee": "0.13"
                }
            ],
            "rateType": "FIXED",
            "status": "OVERPAID",
            "refundFollowUpDepositsForOneTimePayments": true,
            "type": "ONE_TIME",
            "overpaymentPolicy": "EXCESS_REFUND",
            "clientPaymentId": "ltc_overpaid"
        },
        {
            "expectedUniformAmount": "12.98",
            "expectedDepositAmount": "0.08883051",
            "actualUniformAmount": "12.98",
            "locale": "en-US",
            "expectedDisplayAmount": "15.00",
            "paymentInitiatedAt": 1634035977,
            "paymentRequestedAt": 1634035984,
            "actualDepositAmount": "0.08883051",
            "depositCurrency": "LTC",
            "actualDisplayAmount": "15.00",
            "expirationMinutes": 30,
            "paymentId": "6d1e7310-60c0-4448-ac5a-ffdb4f180871",
            "walletAddress": "MRNAvoAr1QVdQqMb6XaiWcNWwBR4DKdUZx",
            "processorType": "BLOCKCHAIN",
            "displayCurrency": "USD",
            "businessId": "dab81a7a-2502-4784-ad34-87e04e5129f0",
            "deposits": [
                {
                    "depositAmount": "0.08883051",
                    "depositCurrency": "LTC",
                    "depositReceivedAt": 1634036563,
                    "displayAmount": "15.00000000",
                    "displayCurrency": "USD",
                    "displayPayableAmount": "14.85000000",
                    "displayServiceFee": "0.15000000",
                    "fromAddress": "ltc1q2gq92a2w6edn7vpff8pv7hd543w8c09d05qesr",
                    "id": "76740364-7849-3eb3-af00-8f635fb316bd",
                    "onChainFee": "0.00000444",
                    "refund": {
                        "amount": "0.00116949",
                        "displayAmount": "0.20",
                        "displayCurrency": "USD",
                        "displayFee": "0.17",
                        "fee": "0.00100000",
                        "reason": "OVERPAYMENT",
                        "status": "NON_REFUNDABLE",
                        "type": "PARTIAL"
                    },
                    "riskScore": "0.12",
                    "settlementCurrency": "USDT",
                    "settlementPayableAmount": "14.82034642",
                    "settlementServiceFee": "0.14970047",
                    "toAddress": "MRNAvoAr1QVdQqMb6XaiWcNWwBR4DKdUZx",
                    "transactionId": "23816f9ad80147419f1fc177c3329afa466991f2943276066ef5e23d2244dc46",
                    "uniformCurrency": "EUR",
                    "uniformPayableAmount": "12.85",
                    "uniformServiceFee": "0.13"
                }
            ],
            "rateType": "FIXED",
            "status": "OVERPAID",
            "refundFollowUpDepositsForOneTimePayments": true,
            "type": "ONE_TIME",
            "overpaymentPolicy": "EXCESS_REFUND",
            "clientPaymentId": "ltc_fixed_overpaid"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
