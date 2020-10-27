# Deposit received time

The second type of event is sent once the transaction is added in a block and there is 1 blockchain confirmation, we trigger a callback notification on your registered endpoint with status `CONFIRMED` All coins support this event. 

This notification is also sent for \(fiat\) card payments - for such payments, the notification is sent once the card of the payer has been charged. The `transactionId` is optional in the context of fiat payments.

> This callback notification is sent on your `depositReceivedCallbackUrl` endpoint.

```javascript
{  
    "actualDepositAmount":0.20915278,
    "actualDisplayAmount":14.01,
    "clientPaymentId":"test-ltc-2",
    "depositAddress":"MT2dMnj3eH2PabKA4ZH4RYQdWAaMkoXbTq",
    "depositCurrency":"LTC",
    "displayCurrency":"EUR",
    "expectedDepositAmount":0.21015278,
    "expectedDisplayAmount":14.00,
    "expirationTime":1566743563,
    "onChainFee":0.00074800,
    "paymentId":"aa77329f-bddb-4ab7-8128-9a9b1a116113",
    "depositId":"95b15c4b-97df-3565-92b6-5006b9a264ea",
    "status":"CONFIRMED",
    "paymentReceivedAt":1566742859,
    "paymentRequestedAt":1566741899,
    "transactionId":"900420600c0bd373e30043089d206d919c1fca6495c4a740f42b3803daa5b980"
}
```

{% hint style="info" %}
The networks of some coins like `XRP` and `XLM` are extremely fast. It takes literally ~1 second to verify and confirm a transaction once it's broadcast on the network. 
{% endhint %}



