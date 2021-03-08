# Get exchange rates \[fiat to fiat\]

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/exchange/rates/fiat" %}
{% api-method-summary %}
Get Exchange rates \[fiat to fiat\]
{% endapi-method-summary %}

{% api-method-description %}
Get the most recent fiat exchange rates.  
Update time: every 30 minutes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="fromCurrency" type="string" required=true %}
Expects fiat currency as base. Supports multiple comma separated values.
{% endapi-method-parameter %}

{% api-method-parameter name="toCurrency" type="string" required=true %}
Expects fiat currency as quote.Supports multiple comma separated values.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
https://payments.finrax.com/api/v1/exchange/rates/fiat?fromCurrency=USD,EUR,GBP&toCurrency=USD,CHF
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



