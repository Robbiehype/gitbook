# 🔒 Get business by ID

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/businesses/:id" method="get" summary="Get Business by ID" %}
{% swagger-description %}
This endpoint allows you to get the business information
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the business 

`UUID`
{% endswagger-parameter %}

{% swagger-response status="200" description="Cake successfully retrieved." %}
```javascript
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
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
Due to security reasons we don't return BusinessID as response from any API calls.\
You can locate the BusinessID in your Finrax organisation account.\
Click on Businesses > Expand Business > Top left corner.
{% endhint %}

### Response schema

| Parameter                   | Type   | Description                                                              |
| --------------------------- | ------ | ------------------------------------------------------------------------ |
| createdAt                   | number | UNIX timestamp when the business got created                             |
| depositReceivedCallbackUrl  | string | URL endpoint to receive callback notifications at broadcast/receive time |
| depositExchangedCallbackUrl | string | URL endpoint to receive callback notifications at exchange time          |
| id                          | string | Unique business identifier UUID                                          |
| name                        | string | Name of your business                                                    |
| settlementCryptoCurrency    | string | Cryptocurrency for settlements                                           |
| settlementCryptoRatio       | string | Fiat/Crypto ratio for deposit allocation                                 |
| settlementFiatCurrency      | string | Fiat currency for settlements. Currently only EUR is supported           |
| supportedDepositCurrencies  | array  | Array with all supported cryptocurrencies of this business               |
| supportedDisplayCurrencies  | array  | Array with all supported fiat currencies for pairing                     |
| theme                       | string | Theme of the checkout page                                               |
| withdrawalCallbackUrl       | string | URL endpoint to receive callbacks at withdrawal completion time          |

