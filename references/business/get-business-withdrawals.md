# 🔒 Get business withdrawals

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/businesses/withdrawals" %}
{% api-method-summary %}
Get business withdrawals
{% endapi-method-summary %}

{% api-method-description %}
Allows you to fetch all withdrawals for a business
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="businessId" type="string" required=true %}
Unique business identifier `UUID`
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Results per request \(Default: 25\)
{% endapi-method-parameter %}

{% api-method-parameter name="coins" type="array" required=false %}
Filter by coins comma delimited `(BTC, ETH, XRP,...)`
{% endapi-method-parameter %}

{% api-method-parameter name="statuses" type="string" required=false %}
Can be used to filter per status . Accepts `NEW`  `PENDING`  `COMPLETED`  `FAILED`
{% endapi-method-parameter %}

{% api-method-parameter name="clientWithdrawId" type="string" required=false %}
Payment identifier of the client
{% endapi-method-parameter %}

{% api-method-parameter name="before" type="integer" required=false %}
End date of the results
{% endapi-method-parameter %}

{% api-method-parameter name="after" type="integer" required=false %}
Start date of the results
{% endapi-method-parameter %}

{% api-method-parameter name="sortBy" type="string" %}
Sort withdrawals by `created`
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Withdrawals fetched successfully
{% endapi-method-response-example-description %}

```javascript
{
  "withdrawals": [
    {
      "withdrawId": "6ff8ceeb-3988-4bde-acb2-acff87092d20",
      "clientWithdrawId": "MyFirstWithdrawal",
      "recipientAddress": "0x394d1b8b60ddb88bf7399322ce1c1208bef8a222",
      "transactionId": "0xbefa34b2fd2dfc9a4810a0dab4edc53b3f950f9eb69bb1e53748c3bf7b082795",
      "initiatedBy": "https://gateway.finrax.com",
      "status": "COMPLETED",
      "displayCurrency": "USD",
      "withdrawCurrency": "POWR",
      "settlementCurrency": "EUR",
      "estimatedDisplayAmount": "20.00",
      "estimatedWithdrawAmount": "403.51379815",
      "actualDisplayAmount": "20.00",
      "actualWithdrawAmount": "403.00000000",
      "settlementDeductedAmount": "18.56",
      "withdrawFee": "5.00000000",
      "displayFee": "0.22",
      "createdAt": 1568712563,
      "exchangedAt": 1568712727
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Example: Fetch business withdrawals filtered by status COMPLETED and coin XRP

{% tabs %}
{% tab title="Request" %}
```javascript
curl --location --request GET 'https://dev-payments.finrax.com/api/v1/withdrawals?businessId=19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd&statuses=COMPLETED&coins=XRP' \
--header 'Content-Type: application/json' \
--header 'Authorization: FRX-API api-key=<your_api_key>,signature=<your_signature>,timestamp=<timestamp>'
```
{% endtab %}

{% tab title="Response" %}
```javascript
{
  "withdrawals": [
    {
      "withdrawId": "a952e1a1-1b75-460f-a9c4-8a19e71c4dfa",
      "clientWithdrawId": "testWithdrawal-3.12",
      "recipientAddress": "rw2ciyaNshpHe7bCHo4bRWq6pqqynnWKQg?dt=4077347672",
      "transactionId": "65DA5799E49DFC4F78F27CB950B6041A9BF7DFC816B31B0D1C0A505054F2A333",
      "initiatedBy": "test@finrax.com",
      "status": "COMPLETED",
      "displayCurrency": "USD",
      "withdrawCurrency": "XRP",
      "settlementCurrency": "USDT",
      "estimatedDisplayAmount": "15.00",
      "estimatedWithdrawAmount": "98.47595300",
      "actualDisplayAmount": "15.00",
      "actualWithdrawAmount": "97.90200000",
      "settlementDeductedAmount": "15.19701700",
      "withdrawFee": "0.25000000",
      "displayFee": "0.04",
      "createdAt": 1584015095,
      "exchangedAt": 1584015188
    },
    {
      "withdrawId": "8e2324e0-d8df-4df4-a25f-6fca0d019a08",
      "clientWithdrawId": "Example-Withdra2al",
      "recipientAddress": "rw2ciyaNshpHe7bCHo4bRWq6pqqynnWKQg?dt=2604946645",
      "transactionId": "08CD48297F8DA16B3BB06AE21266BA2572889552E9EDDA8A24DB3169A96F4BE6",
      "initiatedBy": "test@finrax.com",
      "status": "COMPLETED",
      "displayCurrency": "EUR",
      "withdrawCurrency": "XRP",
      "settlementCurrency": "USDT",
      "estimatedDisplayAmount": "15.00",
      "estimatedWithdrawAmount": "70.05445300",
      "actualDisplayAmount": "15.00",
      "actualWithdrawAmount": "70.02990000",
      "settlementDeductedAmount": "16.43740000",
      "withdrawFee": "0.25000000",
      "displayFee": "0.05",
      "createdAt": 1582998505,
      "exchangedAt": 1582998551
    }
  ]
}
```
{% endtab %}
{% endtabs %}



