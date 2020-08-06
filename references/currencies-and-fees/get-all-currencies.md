# Get all currencies

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/currencies" %}
{% api-method-summary %}
Get all currencies
{% endapi-method-summary %}

{% api-method-description %}
Allows you to list all supported currencies at Finrax
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Currencies fetched successfully
{% endapi-method-response-example-description %}

```javascript
[
    {
        "abbreviation": "BTC",
        "id": "6b339811-c300-4dc5-a1ea-32c5740faebd",
        "isFiat": false,
        "name": "Bitcoin"
    },
    {
        "abbreviation": "BCH",
        "id": "5d9a3f85-e24f-4e45-8d3b-723ba2dcdc06",
        "isFiat": false,
        "name": "Bitcoin Cash"
    },
    {
        "abbreviation": "BTG",
        "id": "efe3b46a-51dd-4ac7-afef-f7d4594a9a68",
        "isFiat": false,
        "name": "Bitcoin Gold"
    },
    {
        "abbreviation": "DASH",
        "id": "023f41d7-24d6-48ea-aa20-558a98df0a57",
        "isFiat": false,
        "name": "Dash"
    },
    {
        "abbreviation": "ETH",
        "id": "2d4215b6-a28c-47d0-a85e-fd668c9f7d8c",
        "isFiat": false,
        "name": "Ethereum"
    },
    ...
    ...
    {
        "abbreviation": "ZAR",
        "id": "8f0244f7-6ec1-4d0d-84a3-cee7fba4e216",
        "isFiat": true,
        "name": "ZAR"
    },
    {
        "abbreviation": "SEK",
        "id": "87db5f43-45bd-4a6c-8a31-42147bce49cb",
        "isFiat": true,
        "name": "SEK"
    },
    {
        "abbreviation": "NZD",
        "id": "3fc623b9-89a0-4426-b402-b85a82727f8b",
        "isFiat": true,
        "name": "NZD"
    },
    {
        "abbreviation": "CNY",
        "id": "aaa7be2a-0d00-4739-b340-d1175e935883",
        "isFiat": true,
        "name": "CNY"
    },
    {
        "abbreviation": "SGD",
        "id": "07f2e35f-319f-4102-b2cc-9d22caea23f8",
        "isFiat": true,
        "name": "SGD"
    },
    {
        "abbreviation": "MYR",
        "id": "b23b9966-ae02-448c-a2b5-ce120846ff93",
        "isFiat": true,
        "name": "MYR"
    }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}





