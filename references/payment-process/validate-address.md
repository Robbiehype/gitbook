# Validate address

{% api-method method="post" host="https://payments.finrax.com" path="/api/v1/addresses/validate" %}
{% api-method-summary %}
Validate address
{% endapi-method-summary %}

{% api-method-description %}
An endpoint for checking if a wallet address is valid according to the coin-specific format.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="coin" type="string" required=true %}
Coin abbreviation like `BTC`  `ETH`  `XRP`
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=true %}
Wallet address to be checked
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns if wallet is valid
{% endapi-method-response-example-description %}

```javascript
{
  "isValid": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



