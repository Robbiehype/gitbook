# Get exchange rates \[single\]

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/exchange/rates/deposit" %}
{% api-method-summary %}
Get exchange rates
{% endapi-method-summary %}

{% api-method-description %}
Get the most recent exchange rates for single cryptocurrency.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="fromCurrency" type="string" required=true %}
Expects supported cryptocurrency such as \(BTC, ETH , XRP, etc.\)
{% endapi-method-parameter %}

{% api-method-parameter name="toCurrency" type="string" required=true %}
Expects supported fiat currency such as \(EUR, USD, GBP, etc.\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
GET /api/v1/rates/9b5cf38d-9490-4131-9fa5-3626d761cbd6/btc\_eur
{% endapi-method-response-example-description %}

```javascript
{
    "base": "BTC",
    "quote": "EUR",
    "price": 4681.89317678
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



