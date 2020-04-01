# Get exchange rates \[multi\]

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/rates/multi/9b5cf38d-9490-4131-9fa5-3626d761cbd6" %}
{% api-method-summary %}
Get exchange rates for multiple currencies
{% endapi-method-summary %}

{% api-method-description %}
Allows you to fetch most recent exchange rates for all cryptocurrencies. Supports all fiat currencies for pairing e.g. you can get the exchange rates for Bitcoin into USD,GBP,EUR,TRY etc. with one request.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="from" type="string" %}
Accepts all supported **cryptocurrencies** comma delimited
{% endapi-method-parameter %}

{% api-method-parameter name="to" type="string" %}
Accepts all supported **fiat** currencies comma delimited
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Example /api/v1/rates/multi/9b5cf38d-9490-4131-9fa5-3626d761cbd6?from=BTC,XRP,ETH&to=EUR,USD,GBP
{% endapi-method-response-example-description %}

```javascript
{
    "EUR": {
        "BTC": 4692.0415,
        "XRP": 0.131002,
        "ETH": 102.6666
    },
    "GBP": {
        "BTC": 4261.4529,
        "XRP": 0.11898,
        "ETH": 93.2449
    },
    "USD": {
        "BTC": 5152.8,
        "XRP": 0.143866,
        "ETH": 112.7484
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



