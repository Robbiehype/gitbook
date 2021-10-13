# Validate address

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/addresses/validate" method="post" summary="Validate address" %}
{% swagger-description %}
An endpoint for checking if a wallet address is valid according to the coin-specific format.
{% endswagger-description %}

{% swagger-parameter in="body" name="coin" type="string" %}
Coin abbreviation like 

`BTC`

  

`ETH`

  

`XRP`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="string" %}
Wallet address to be checked
{% endswagger-parameter %}

{% swagger-response status="200" description="Returns if wallet is valid" %}
```javascript
{
  "isValid": true
}
```
{% endswagger-response %}
{% endswagger %}

