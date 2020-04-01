# Get exchange rates \[single\]

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/rates/9b5cf38d-9490-4131-9fa5-3626d761cbd6/:pair" %}
{% api-method-summary %}
Get exchange rates
{% endapi-method-summary %}

{% api-method-description %}
Get the most recent exchange rates for single cryptocurrency.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="pair" type="string" required=false %}
Accepts all supported crypto\_fiat pairs `btc_eur,btc_usd, xrp_gbp, eth_pln, etc...` 
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
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



