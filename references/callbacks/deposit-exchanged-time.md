# Deposit exchanged time

The key value of using Finrax Payment Gateway is its fast exchange time and fair exchange rates. We aim to exchange all deposits in under 1 minute after it has been received. In addition, once the exchange happens we trigger a callback notification to inform you about the settlement amount that you can later withdraw. 

> This callback notification is sent on your `depositExchangedCallbackUrl` endpoint.

```javascript
{
  "actualDepositAmount": 0.00258097,
  "clientPaymentId": "MySecondDeposit",
  "depositAddress": "33DiE7SaGHX8CMShjkvQRNudGKtEfxTmsS",
  "depositCurrency": "BTC",
  "displayCurrency": "USD",
  "displayExchangedAmount": 19.99,
  "displayPayableAmount": 19.80,
  "displayServiceFee": 0.19,
  "expectedDepositAmount": 0.00258097,
  "paymentExchangedAt": 1579169466,
  "paymentId": "0d408fb3-8d57-430d-890d-090740b7cd03",
   "depositId":"95b15c4b-97df-3565-92b6-5006b9a264ea",
  "paymentReceivedAt": 1579169399,
  "settlementCurrency": "EUR",
  "settlementExchangedAmount": 17.92,
  "settlementPayableAmount": 17.74,
  "settlementServiceFee": 0.18,
  "transactionId": "4b6b67367aea858b60cfc112d80ce0b2c8317aecd7437df4937d0b262849c6f2"
}
```

{% hint style="warning" %}
We don't suggest using this callback notification for crediting users' deposits as it will take longer until the funds are available for use.
{% endhint %}

{% hint style="info" %}
We do our best to keep the volatility exposure close to zero. Our last analysis shows 0.018% volatility exposure on a month by month basis.
{% endhint %}



