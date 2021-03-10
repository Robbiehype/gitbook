# Get exchange rates \[crypto to fiat\]

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/exchange/rates/deposit" %}
{% api-method-summary %}
Get Exchange Rates \[crypto to fiat\]
{% endapi-method-summary %}

{% api-method-description %}
Get the most recent exchange rates for cryptocurrencies vs. fiat currencies.  
Update time: instant
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="fromCurrency" type="string" required=true %}
Expects cryptocurrency such as \(BTC, ETH , XRP, etc.\). Supports multiple comma separated values.
{% endapi-method-parameter %}

{% api-method-parameter name="toCurrency" type="string" required=true %}
Expects fiat currency such as \(EUR, USD, GBP, etc.\). Supports multiple comma separated values.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
https://payments.finrax.com/api/v1/exchange/rates/deposit?fromCurrency=BTC,ETH,XRP&toCurrency=EUR,USD
{% endapi-method-response-example-description %}

```javascript
{
"ETH": {
"EUR": "1467.8",
"USD": "1741.1"
},
"BTC": {
"EUR": "42798",
"USD": "50770"
},
"XRP": {
"EUR": "0.40227",
"USD": "0.4772"
}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



