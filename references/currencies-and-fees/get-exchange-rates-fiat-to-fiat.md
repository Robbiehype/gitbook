# Get exchange rates \[fiat to fiat]

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/exchange/rates/fiat" method="get" summary="Get Exchange rates [fiat to fiat]" %}
{% swagger-description %}
Get the most recent fiat exchange rates.

\


Update time: every 30 minutes.
{% endswagger-description %}

{% swagger-parameter in="query" name="fromCurrency" type="string" %}
Expects fiat currency as base. Supports multiple comma separated values.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="toCurrency" type="string" %}
Expects fiat currency as quote.Supports multiple comma separated values.
{% endswagger-parameter %}

{% swagger-response status="200" description="https://payments.finrax.com/api/v1/exchange/rates/fiat?fromCurrency=USD,EUR,GBP&toCurrency=USD,CHF" %}
```javascript
{
"USD": {
"USD": "1",
"CHF": "0.935074"
},
"EUR": {
"USD": "1.186102",
"CHF": "1.109093"
},
"GBP": {
"USD": "1.38394",
"CHF": "1.294086"
}
}
```
{% endswagger-response %}
{% endswagger %}

