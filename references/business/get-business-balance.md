# 🔒 Get business balance

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/balances/:id" method="get" summary="Get business balance" %}
{% swagger-description %}
Allows you to fetch the current business balance and allocation ratio of a given business.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="integer" %}
Unique business identifier
{% endswagger-parameter %}

{% swagger-response status="200" description="Cake successfully retrieved." %}
```javascript
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
{% endswagger-response %}
{% endswagger %}

