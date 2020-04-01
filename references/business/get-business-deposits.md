# Get business deposits 🔒

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
      "actualDepositAmount": "10.32000000",
      "actualDisplayAmount": "13.99",
      "businessId": "19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd",
      "clientPaymentId": "OMGtoUSDT-3",
      "depositCurrency": "OMG",
      "deposits": [
        {
          "depositAmount": "10.32000000",
          "depositCurrency": "OMG",
          "depositExchangedAt": 1565696708,
          "depositReceivedAt": 1565696350,
          "displayAmount": "13.99",
          "displayCurrency": "USD",
          "displayExchangedAmount": "13.98000000",
          "displayPayableAmount": "13.77000000",
          "displayServiceFee": "0.21000000",
          "id": "b6f97c95-75c2-39ac-b5db-eadad2f0321a",
          "onChainFee": "0.00208376",
          "settlementCurrency": "USDT",
          "settlementExchangedAmount": "14.02384800",
          "settlementPayableAmount": "13.81349028",
          "settlementServiceFee": "0.21035772",
          "toAddress": "0x2d31c7d9bef990c4d5ff61a1f6cb622f90d0a3e2",
          "transactionId": "0xb27e8e7d583f2b4964e2d401da38c3b7cae00fedc893ba825a84beaaac95a94d"
        }
      ],
      "displayCurrency": "USD",
      "expectedDepositAmount": "10.32524522",
      "expectedDisplayAmount": "14.00",
      "expirationMinutes": 30,
      "locale": "en-US",
      "paymentId": "138b4fd5-96fb-4bfe-be60-97641cdb818c",
      "paymentInitiatedAt": 1565695971,
      "paymentRequestedAt": 1565695990,
      "status": "DEPOSITED",
      "walletAddress": "0x2d31c7d9bef990c4d5ff61a1f6cb622f90d0a3e2"
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
            "actualDepositAmount": "0.00126312",
            "actualDisplayAmount": "11.96",
            "businessId": "19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd",
            "clientPaymentId": "Mangusta",
            "depositCurrency": "BTC",
            "deposits": [
                {
                    "depositAmount": "0.00126312",
                    "depositCurrency": "BTC",
                    "depositExchangedAt": 1572192682,
                    "depositReceivedAt": 1572192592,
                    "displayAmount": "11.96",
                    "displayCurrency": "USD",
                    "displayExchangedAmount": "12.00000000",
                    "displayPayableAmount": "11.64000000",
                    "displayServiceFee": "0.36000000",
                    "id": "15429934-35b0-358e-aec7-9672f3bff156",
                    "onChainFee": "0.00006488",
                    "rbfFlag": false,
                    "settlementCurrency": "EUR",
                    "settlementExchangedAmount": "10.80000000",
                    "settlementPayableAmount": "10.48000000",
                    "settlementServiceFee": "0.32000000",
                    "toAddress": "31oVuM95i8d8NWdyNYT6yBn5FNsTirXjHz",
                    "transactionId": "1f17a0fdeb7f69f610d75102f3d410ed128725da46869da8f6c09a7d8eabb983"
                }
            ],
            "displayCurrency": "USD",
            "expectedDepositAmount": "0.00126312",
            "expectedDisplayAmount": "12.00",
            "expirationMinutes": 30,
            "isSuspicious": false,
            "locale": "en-US",
            "paymentId": "5dbd6591-5626-4f25-b0ed-70b55545f5c3",
            "paymentInitiatedAt": 1572190690,
            "paymentRequestedAt": 1572190743,
            "status": "DEPOSITED",
            "walletAddress": "31oVuM95i8d8NWdyNYT6yBn5FNsTirXjHz"
        },
        {
            "actualDepositAmount": "0.00172820",
            "actualDisplayAmount": "13.99",
            "businessId": "19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd",
            "clientPaymentId": "BTCZeroConfirm-Test",
            "depositCurrency": "BTC",
            "deposits": [
                {
                    "depositAmount": "0.00172820",
                    "depositCurrency": "BTC",
                    "depositExchangedAt": 1570182307,
                    "depositReceivedAt": 1570178720,
                    "displayAmount": "13.99",
                    "displayCurrency": "USD",
                    "displayExchangedAmount": "14.04000000",
                    "displayPayableAmount": "13.62000000",
                    "displayServiceFee": "0.42000000",
                    "id": "7ab36baa-245f-34f4-af41-795ecb7d4ef0",
                    "onChainFee": "0.00006931",
                    "rbfFlag": false,
                    "settlementCurrency": "USDT",
                    "settlementExchangedAmount": "14.02263208",
                    "settlementPayableAmount": "13.60195312",
                    "settlementServiceFee": "0.42067896",
                    "toAddress": "3K9xCMhSbMmidB2itcYuBdLhngRfWKAVa3",
                    "transactionId": "6d7f506734c7b99a331c9f9f1914d1f380a7eb87467d642cc75ff5221f880366"
                }
            ],
            "displayCurrency": "USD",
            "expectedDepositAmount": "0.00172820",
            "expectedDisplayAmount": "14.00",
            "expirationMinutes": 30,
            "isSuspicious": false,
            "locale": "en-US",
            "paymentId": "12aa975c-45ed-46de-9e8d-aa8c38fc736c",
            "paymentInitiatedAt": 1570178603,
            "paymentRequestedAt": 1570178612,
            "status": "DEPOSITED",
            "walletAddress": "3K9xCMhSbMmidB2itcYuBdLhngRfWKAVa3"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

