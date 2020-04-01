# Deposit broadcast time

Once the end user sends funds from his wallet, a record will be broadcast on the blockchain. We listen for blockchain events and as soon as we _see_ a new transfer on the designated wallet address, we trigger a callback notification on your endpoint. The status of this transaction is `UNCONFIRMED` We run internal algorithms to make sure that it will not result in a [double spent attempt](https://coinsutra.com/bitcoin-double-spending/). However we suggest putting a threshold on the amounts you are willing to credit while still in `UNCONFIRMED`status.

> This callback notification is sent on your `depositReceivedCallbackUrl` endpoint

```javascript
{  
"actualDepositAmount":0.20915278,
"actualDisplayAmount":13.99,
"clientPaymentId":"MyFirstDeposit",
"depositAddress":"MT2dMnj3eH2PabKA4ZH4RYQdWAaMkoXbTq",
"depositCurrency":"LTC",
"displayCurrency":"EUR",
"expectedDepositAmount":0.21015278,
"expectedDisplayAmount":14.00,
"expirationTime":1566743563,
"onChainFee":0.00074800,
"paymentId":"aa77329f-bddb-4ab7-8128-9a9b1a116113",
"status":"UNCONFIRMED",
"paymentReceivedAt":1566742859,
"paymentRequestedAt":1566741899,
"transactionId":"900420600c0bd373e30043089d206d919c1fca6495c4a740f42b3803daa5b980"
}
```

{% hint style="success" %}
Using this callback notification makes a huge difference in regard to speed. This will allow you to credit deposits in a matter of seconds instead of minutes.
{% endhint %}

{% hint style="info" %}
On average a Bitcoin transaction to be included in a block requires ~15 minutes. By using our callback at broadcast time you'll be able to credit Bitcoin deposits in less than 10 seconds.
{% endhint %}



