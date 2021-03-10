# 🔒 Get business deposits

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/businesses/:id/payments" %}
{% api-method-summary %}
Get business deposits
{% endapi-method-summary %}

{% api-method-description %}
Allows you to get all deposits per business ID
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the business
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="coins" type="array" required=false %}
List of coins comma delimited  `(BTC,ETH,XRP,...)`
{% endapi-method-parameter %}

{% api-method-parameter name="statuses" type="string" required=false %}
Accepts the following  
`NEW` `PENDING`  `DEPOSITED`  `AWAITING`  `EXPIRED`
{% endapi-method-parameter %}

{% api-method-parameter name="paymentId" type="string" required=false %}
Unique payment identifier `UUID`
{% endapi-method-parameter %}

{% api-method-parameter name="clientPaymentId" type="string" required=false %}
Payment ID provided by the client
{% endapi-method-parameter %}

{% api-method-parameter name="descending" type="boolean" required=false %}
Sort results in descending order
{% endapi-method-parameter %}

{% api-method-parameter name="before" type="number" required=false %}
End date of the report `UNIX`
{% endapi-method-parameter %}

{% api-method-parameter name="after" type="number" required=false %}
Start date of the report `UNIX`
{% endapi-method-parameter %}

{% api-method-parameter name="sortBy" type="string" required=true %}
Sort payments by `status, created` 
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=true %}
Limit of the results per request \(max 2000\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Deposits fetched successfully
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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
{% endtab %}
{% endtabs %}

