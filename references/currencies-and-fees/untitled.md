# Get withdrawal \(on-chain\) fees

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/fees/withdraw/:coin" %}
{% api-method-summary %}
Get withdrawal \(on-chain\) fees
{% endapi-method-summary %}

{% api-method-description %}
Finrax does not cover the associated on-chain fees for crypto withdrawals. This endpoint allows you to get the current on-chain fees. You can add queries to display the fees in fiat currency.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="coin" type="string" %}
Coin abbreviation `BTC`  `ETH`  `XRP`
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="displayCurrency" type="string" %}
Accepts all supported fiat currencies like `EUR`  `USD`  `GBP`
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Withdrawal fees fetched successfully
{% endapi-method-response-example-description %}

```javascript
{
"displayCurrency": "EUR",
"fees": [
    {
        "withdrawFee": "0.01",
        "displayWithdrawFee": "0.0005",
        "withdrawCurrency": "XLM",
        "withdrawAvailable": true,
        "withdrawPrecision": 7
    },
    {
        "withdrawFee": "6818",
        "displayWithdrawFee": "1.5807",
        "withdrawCurrency": "NPXS",
        "withdrawAvailable": true,
        "withdrawPrecision": 8
    },
    {
        "withdrawFee": "1.02",
        "displayWithdrawFee": "0.9141",
        "withdrawCurrency": "PAX",
        "withdrawAvailable": true,
        "withdrawPrecision": 8
    },
    {
        "withdrawFee": "1.26",
        "displayWithdrawFee": "0.8550",
        "withdrawCurrency": "OMG",
        "withdrawAvailable": true,
        "withdrawPrecision": 8
    },
    ...
    ...
    ...
    {
        "withdrawFee": "660",
        "displayWithdrawFee": "0.8671",
        "withdrawCurrency": "KEY",
        "withdrawAvailable": true,
        "withdrawPrecision": 8
    },
    {
    "withdrawFee": "2236",
    "displayWithdrawFee": "1.3824",
    "withdrawCurrency": "HOT",
    "withdrawAvailable": true,
    "withdrawPrecision": 8
    }
 ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



