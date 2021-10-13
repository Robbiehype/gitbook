# Get exchange rates \[crypto to fiat]

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/exchange/rates/deposit" method="get" summary="Get Exchange Rates [crypto to fiat]" %}
{% swagger-description %}
Get the most recent exchange rates for cryptocurrencies vs. fiat currencies.

\


Update time: instant
{% endswagger-description %}

{% swagger-parameter in="query" name="fromCurrency" type="string" %}
Expects cryptocurrency such as (BTC, ETH , XRP, etc.). Supports multiple comma separated values.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="toCurrency" type="string" %}
Expects fiat currency such as (EUR, USD, GBP, etc.). Supports multiple comma separated values.
{% endswagger-parameter %}

{% swagger-response status="200" description="https://payments.finrax.com/api/v1/exchange/rates/deposit?fromCurrency=BTC,ETH,XRP&toCurrency=EUR,USD" %}
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
{% endswagger-response %}
{% endswagger %}

