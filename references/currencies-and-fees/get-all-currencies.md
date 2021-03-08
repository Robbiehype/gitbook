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
"isERC20": false,
"isFiat": false,
"model": "UTXO",
"name": "Bitcoin"
},
{
"abbreviation": "ETH",
"id": "2d4215b6-a28c-47d0-a85e-fd668c9f7d8c",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Ethereum"
},
{
"abbreviation": "LTC",
"id": "5ad13ca1-eef9-4fa4-b4c2-a9705754e904",
"isERC20": false,
"isFiat": false,
"model": "UTXO",
"name": "Litecoin"
},
{
"abbreviation": "XRP",
"id": "16cc4929-b84b-4020-85e2-a7455f538ec0",
"isERC20": false,
"isFiat": false,
"model": "ACCOUNT",
"name": "Ripple"
},
{
"abbreviation": "AION",
"id": "710af8ad-5d87-4ab4-b095-f73d0093caa4",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "AION"
},
{
"abbreviation": "BAT",
"id": "52175260-7b95-49ec-9291-179774852a2b",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Basic Attention Token"
},
{
"abbreviation": "BNT",
"id": "b4b13d29-2a04-4a9f-9ba1-30facd704a50",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Bancor"
},
{
"abbreviation": "CVC",
"id": "4f59b7db-7ebc-47d2-9ac4-c097d3905d56",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Civic"
},
{
"abbreviation": "ENJ",
"id": "5503b626-bb02-4613-918d-d0a0b0253d28",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Enjin Coin"
},
{
"abbreviation": "FUN",
"id": "255d757c-ccf6-45c5-9001-b081b347288f",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "FunFair"
},
{
"abbreviation": "KNC",
"id": "80bc69aa-589f-4c07-8caf-11b647ac3e97",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Kyber Network"
},
{
"abbreviation": "LINK",
"id": "fb0882fe-0e46-45c6-80db-bcf00976885b",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Chainlink"
},
{
"abbreviation": "MITH",
"id": "c16ab9c5-b836-44ad-a5bd-b968fce7c01f",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Mithril"
},
{
"abbreviation": "MTL",
"id": "d936b16a-7847-4370-8064-0d30ef2d408a",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Metal"
},
{
"abbreviation": "OMG",
"id": "c38e70eb-ba2f-4ece-b0b3-f78c1fb1d14e",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "OmiseGo"
},
{
"abbreviation": "REP",
"id": "164af0aa-336b-4157-b966-152658e4fd42",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Augur"
},
{
"abbreviation": "ZIL",
"id": "e5ee83cf-0e8d-4d19-a605-00869f46547d",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Zilliqa"
},
{
"abbreviation": "EUR",
"id": "865d0616-52b4-4a8e-afff-d4293300d49a",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "Euro"
},
{
"abbreviation": "USD",
"id": "d3a8ca8d-ce1e-48f8-bc93-3785ebefb363",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "United States Dollar"
},
{
"abbreviation": "TRY",
"id": "08018a78-9ed1-4718-8ee3-56e97f04f775",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "Turkish Lira"
},
{
"abbreviation": "BGN",
"id": "6b2b1ab7-d33c-4e9e-b5ac-b1ced271c023",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "Bulgarian Lev"
},
{
"abbreviation": "GBP",
"id": "a3d1f474-9e8b-4f50-9576-534b7dfdd65a",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "Pound Sterling"
},
{
"abbreviation": "XLM",
"id": "f9b4c1a2-c025-4e41-a66b-855bfeb50a76",
"isERC20": false,
"isFiat": false,
"model": "ACCOUNT",
"name": "Stellar Lumens"
},
{
"abbreviation": "INR",
"id": "688d80de-38b0-4103-aadc-0881d1681b12",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "INR"
},
{
"abbreviation": "BRL",
"id": "31686eb9-07d0-45e3-af9e-6c63834fba9c",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "BRL"
},
{
"abbreviation": "ISK",
"id": "56ebe837-ce90-4a58-a67a-c81f5ecb8ede",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "ISK"
},
{
"abbreviation": "MXN",
"id": "24d75ed0-11e7-4f97-99ae-b0f35443553c",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "MXN"
},
{
"abbreviation": "PLN",
"id": "fe17f443-1d19-4604-8aa1-4c64d8b6b6c0",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "PLN"
},
{
"abbreviation": "PHP",
"id": "3520dd84-eac7-4e60-93b6-d42437a31b96",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "PHP"
},
{
"abbreviation": "NOK",
"id": "ea00c7a8-09f4-4086-9b33-b75375f21b1a",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "NOK"
},
{
"abbreviation": "IDR",
"id": "038a90e4-6dc6-470c-92af-7a80ac8fc309",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "IDR"
},
{
"abbreviation": "JPY",
"id": "cd9fbc94-82e0-4b65-ba32-a69613d78ba5",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "JPY"
},
{
"abbreviation": "RUB",
"id": "be4298a9-d466-4e01-a3c2-a0348a959b85",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "RUB"
},
{
"abbreviation": "HRK",
"id": "f1787f37-ff0a-40a6-bafd-6b6550db0f4d",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "HRK"
},
{
"abbreviation": "RON",
"id": "ee0f711d-60dd-4c5e-9df4-eb04a1643f3c",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "RON"
},
{
"abbreviation": "HUF",
"id": "b0bd37cb-c5d1-4dc1-9c47-3246f63eed50",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "HUF"
},
{
"abbreviation": "CHF",
"id": "64f83576-c028-4fd2-9035-5c82cb23a7c6",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "CHF"
},
{
"abbreviation": "AUD",
"id": "2814ba27-200c-4bcc-87d9-ee123ed715cc",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "AUD"
},
{
"abbreviation": "HKD",
"id": "13938b6c-637c-4849-beb8-0666d7469a62",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "HKD"
},
{
"abbreviation": "KRW",
"id": "0cbf3148-46c7-45af-89cb-7be2ddd1eac8",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "KRW"
},
{
"abbreviation": "CAD",
"id": "69ea89b4-3153-4b8c-8062-ed3db4fad0cb",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "CAD"
},
{
"abbreviation": "DKK",
"id": "1f35beb3-b1e3-48ca-87a2-dcab8cfe7cff",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "DKK"
},
{
"abbreviation": "ILS",
"id": "297d5cf8-67e1-4e4e-aa6f-86460e483bde",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "ILS"
},
{
"abbreviation": "THB",
"id": "df4b1e6f-62c5-4e25-8735-d53be2bea105",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "THB"
},
{
"abbreviation": "CZK",
"id": "57721d56-f22b-4260-8943-2affe9e525ac",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "CZK"
},
{
"abbreviation": "ZAR",
"id": "8f0244f7-6ec1-4d0d-84a3-cee7fba4e216",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "ZAR"
},
{
"abbreviation": "SEK",
"id": "87db5f43-45bd-4a6c-8a31-42147bce49cb",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "SEK"
},
{
"abbreviation": "NZD",
"id": "3fc623b9-89a0-4426-b402-b85a82727f8b",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "NZD"
},
{
"abbreviation": "BCH",
"id": "5d9a3f85-e24f-4e45-8d3b-723ba2dcdc06",
"isERC20": false,
"isFiat": false,
"model": "UTXO",
"name": "Bitcoin Cash"
},
{
"abbreviation": "CNY",
"id": "aaa7be2a-0d00-4739-b340-d1175e935883",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "CNY"
},
{
"abbreviation": "SGD",
"id": "07f2e35f-319f-4102-b2cc-9d22caea23f8",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "SGD"
},
{
"abbreviation": "MYR",
"id": "b23b9966-ae02-448c-a2b5-ce120846ff93",
"isERC20": false,
"isFiat": true,
"model": "FIAT",
"name": "MYR"
},
{
"abbreviation": "USDT",
"id": "21fe04a9-aed6-454a-9761-98319357a75f",
"isERC20": true,
"isFiat": false,
"model": "ACCOUNT",
"name": "Tether"
}
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}





