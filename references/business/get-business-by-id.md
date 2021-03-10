# 🔒 Get business by ID

{% api-method method="get" host="https://payments.finrax.com" path="/api/v1/businesses/:id" %}
{% api-method-summary %}
Get Business by ID
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get the business information
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the business `UUID`
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
    "createdAt": 1565103182,
    "depositExchangedCallbackUrl": "https://crypto-only-usdt.free.beeceptor.com",
    "depositReceivedCallbackUrl": "https://crypto-only-usdt.free.beeceptor.com",
    "id": "19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd",
    "name": "Crypto Only USDT",
    "settlementCryptoCurrency": "USDT",
    "settlementCryptoRatio": "1.00",
    "settlementFiatCurrency": "EUR",
    "supportedDepositCurrencies": [
        "BAT",
        "DASH",
        "KNC",
        "ENJ",
        "XRP",
        "BNT",
        "FUN",
        "ETH",
        "LINK",
        "LRC",
        "CVC",
        "LTC",
        "REP",
        "OMG",
        "USDT",
        "AION",
        "BTC",
        "XLM",
        "MITH",
        "EOS",
        "ZIL",
        "MTL",
        "BCH"
    ],
    "supportedDisplayCurrencies": [
        "PLN",
        "CAD",
        "HKD",
        "AUD",
        "SEK",
        "TRY",
        "BRL",
        "KRW",
        "CZK",
        "BGN",
        "GBP",
        "MXN",
        "THB",
        "ISK",
        "SGD",
        "CHF",
        "INR",
        "CNY",
        "PHP",
        "RON",
        "DKK",
        "JPY",
        "HUF",
        "MYR",
        "USD",
        "RUB",
        "NZD",
        "IDR",
        "EOS",
        "ILS",
        "NOK",
        "EUR",
        "ZAR",
        "HRK"
    ],
    "theme": "LIGHT",
    "withdrawalCallbackUrl": "https://crypto-only-usdt.free.beeceptor.com"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Due to security reasons we don't return BusinessID as response from any API calls.  
You can locate the BusinessID in your Finrax organisation account.  
Click on Businesses &gt; Expand Business &gt; Top left corner.
{% endhint %}

### Response schema

| Parameter | Type | Description |
| :--- | :--- | :--- |
| createdAt | number | UNIX timestamp when the business got created |
| depositReceivedCallbackUrl | string | URL endpoint to receive callback notifications at broadcast/receive time |
| depositExchangedCallbackUrl | string | URL endpoint to receive callback notifications at exchange time |
| id | string | Unique business identifier UUID |
| name | string | Name of your business |
| settlementCryptoCurrency | string | Cryptocurrency for settlements |
| settlementCryptoRatio | string | Fiat/Crypto ratio for deposit allocation |
| settlementFiatCurrency | string | Fiat currency for settlements. Currently only EUR is supported |
| supportedDepositCurrencies | array | Array with all supported cryptocurrencies of this business |
| supportedDisplayCurrencies | array | Array with all supported fiat currencies for pairing |
| theme | string | Theme of the checkout page |
| withdrawalCallbackUrl | string | URL endpoint to receive callbacks at withdrawal completion time |



