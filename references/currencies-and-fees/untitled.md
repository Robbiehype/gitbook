# Get withdrawal \(on-chain\) fees

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/fees/withdraw/:coin" %}
{% api-method-summary %}
Get withdrawal \(on-chain\) fees & minimum withdrawal amounts
{% endapi-method-summary %}

{% api-method-description %}
Finrax does not cover the associated on-chain fees for crypto withdrawals. This endpoint allows you to get the current on-chain fees and minimum withdrawal amounts per coin. You can add a query param to display the fees and minimum amounts in fiat currency.
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
    "displayCurrency": "USD",
    "fees": [
        {
            "withdrawFee": "3",
            "displayWithdrawFee": "3.0000",
            "mininumWithdrawableAmount": "13.0000",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "USDT",
            "withdrawAvailable": true,
            "withdrawPrecision": 6
        },
        {
            "withdrawFee": "0.1",
            "displayWithdrawFee": "0.4452",
            "mininumWithdrawableAmount": "2.9203",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "EOS",
            "withdrawAvailable": true,
            "withdrawPrecision": 4
        },
        {
            "withdrawFee": "0.005",
            "displayWithdrawFee": "3.0234",
            "mininumWithdrawableAmount": "0.0215",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "ETH",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.001",
            "displayWithdrawFee": "0.0873",
            "mininumWithdrawableAmount": "0.1490",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "LTC",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "25",
            "displayWithdrawFee": "4.8783",
            "mininumWithdrawableAmount": "66.6219",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "LRC",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "1.3",
            "displayWithdrawFee": "5.3889",
            "mininumWithdrawableAmount": "3.1361",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "OMG",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "4.85",
            "displayWithdrawFee": "4.9524",
            "mininumWithdrawableAmount": "12.7312",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "KNC",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "1153",
            "displayWithdrawFee": "4.8862",
            "mininumWithdrawableAmount": "3067.6354",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "FUN",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.35",
            "displayWithdrawFee": "4.7936",
            "mininumWithdrawableAmount": "0.9492",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "LINK",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "12",
            "displayWithdrawFee": "4.4011",
            "mininumWithdrawableAmount": "35.4454",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "MTL",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "4.63",
            "displayWithdrawFee": "4.9409",
            "mininumWithdrawableAmount": "12.1819",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "BNT",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.002",
            "displayWithdrawFee": "0.2129",
            "mininumWithdrawableAmount": "0.1221",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "DASH",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.25",
            "displayWithdrawFee": "0.1539",
            "mininumWithdrawableAmount": "21.1164",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "XRP",
            "withdrawAvailable": true,
            "withdrawPrecision": 6
        },
        {
            "withdrawFee": "31",
            "displayWithdrawFee": "4.7294",
            "mininumWithdrawableAmount": "85.2121",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "ENJ",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "19",
            "displayWithdrawFee": "4.6554",
            "mininumWithdrawableAmount": "53.0566",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "BAT",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.01",
            "displayWithdrawFee": "0.0018",
            "mininumWithdrawableAmount": "71.1899",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "XLM",
            "withdrawAvailable": true,
            "withdrawPrecision": 7
        },
        {
            "withdrawFee": "0.1",
            "displayWithdrawFee": "0.0081",
            "mininumWithdrawableAmount": "159.5460",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "AION",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.01",
            "displayWithdrawFee": "0.0003",
            "mininumWithdrawableAmount": "385.6456",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "ZIL",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.31",
            "displayWithdrawFee": "4.9025",
            "mininumWithdrawableAmount": "0.8220",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "REP",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "39",
            "displayWithdrawFee": "4.5601",
            "mininumWithdrawableAmount": "111.1828",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "CVC",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "5.11",
            "displayWithdrawFee": "0.0305",
            "mininumWithdrawableAmount": "2177.0316",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "MITH",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.001",
            "displayWithdrawFee": "0.2864",
            "mininumWithdrawableAmount": "0.0454",
            "displayMinimumWithdrawableAmount": "13.0000",
            "withdrawCurrency": "BCH",
            "withdrawAvailable": true,
            "withdrawPrecision": 8
        },
        {
            "withdrawFee": "0.0005",
            "displayWithdrawFee": "9.6313",
            "mininumWithdrawableAmount": "0.0010",
            "displayMinimumWithdrawableAmount": "19.2627",
            "withdrawCurrency": "BTC",
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



