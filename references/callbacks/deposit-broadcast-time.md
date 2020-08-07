# Deposit broadcast time

Once the end user sends funds from their wallet, a transaction-specific events will be broadcasted on the blockchain. We listen for such blockchain events and will send them to you via an endpoint provided by you when creating your business through the dashboard. There are two types of block-chain events that we propagate to you:  
  
The first event is sent as soon as we _see_ a new deposit transfer broadcasted on the designated wallet address. At this stage the status of the transaction is still `UNCONFIRMED` We run an internal probabilistic algorithm to help us identify [double spent attempts](https://coinsutra.com/bitcoin-double-spending/) or illicit transactions. If we detect such a case we won't propagate this event to you systemically and will instead contact you about it. Note that only UTXO-based coins \(BTC, LTC, BCH etc..\) have such an event, whereas account-based coins \(ETH, ERC20, XLM, XRP\) don't .

> The following callback notification will be sent on your `depositReceivedCallbackUrl` endpoint

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
    "depositId":"95b15c4b-97df-3565-92b6-5006b9a264ea",
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



