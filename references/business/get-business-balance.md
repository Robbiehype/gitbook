# Get business balance 🔒

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/businesses/:id/balance" %}
{% api-method-summary %}
Get business balance
{% endapi-method-summary %}

{% api-method-description %}
Allows you to fetch the current business balance and allocation ratio of a given business.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
Unique business identifier
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "businessId": "19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd",
    "businessName": "My Awesome Business",
    "fiatAllocation": "0.9",
    "settlementFiatCurrency": "EUR",
    "settlementFiatAmount": "250000",
    "displayFiatAmount": "250000",
    "cryptoAllocation": "0.1",
    "settlementCryptoCurrency": "USDT",
    "settlementCryptoAmount": "25000",
    "displayCryptoAmount": "22452.50"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



