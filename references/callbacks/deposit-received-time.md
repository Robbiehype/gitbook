# Deposit received notification

Once the end-user sends funds from their wallet, transaction-specific events will be broadcasted on the blockchain. We listen for such blockchain events and will send them to you via an endpoint provided by you when creating your business through the [dashboard](http://dashboard.finrax.com/). 

Based on our [instant deposit ](https://blog.finrax.com/guides/instant-deposits)feature an event will be sent to you as soon as we _see_ a new deposit transfer broadcasted on the designated wallet address. At this stage, the status of the transaction is still `UNCONFIRMED` We run an internal probabilistic algorithm to help us identify [double spent attempts](https://coinsutra.com/bitcoin-double-spending/) or illicit transactions. If we detect such a case we won't propagate this event to you systemically and will instead contact you about it. Note that only UTXO-based coins \(BTC, LTC, BCH etc..\) have such an event, whereas account-based coins \(ETH, ERC20, XLM, XRP\) don't.

If the deposit doesn't meet our [instant deposit](https://blog.finrax.com/guides/instant-deposits) conditions a notification will be sent once the transaction is added in a block and there is 1 blockchain confirmation.

> This callback notification is sent on your `depositReceivedCallbackUrl` endpoint.

```javascript
{
  "actualDepositAmount": 0.14840339,
  "actualDisplayAmount": 15,
  "clientPaymentId": "payment-example-3",
  "depositAddress": "M8r37BqrgHNGU5DkGRiWY8rAopVCWvmsuk",
  "depositCurrency": "LTC",
  "depositId": "5979560a-27f1-3558-95af-02d7f64a3f25",
  "displayCurrency": "EUR",
  "displayServiceFee": 0.08,
  "expectedDepositAmount": 0.14840339,
  "expectedDisplayAmount": 15,
  "expirationTime": 1611758532,
  "onChainFee": 0.00000426,
  "paymentId": "9c1bfc14-e658-446d-bba7-f7ea8eb21756",
  "paymentReceivedAt": 1611757019,
  "paymentRequestedAt": 1611756744,
  "rateType": "FIXED",
  "settlementAmount": 15,
  "settlementCurrency": "EUR",
  "settlementServiceFee": 0.08,
  "status": "CONFIRMED",
  "transactionId": "49fd4601aeac8694f014b9d27714ccf639db427ea6ad3c0b831eb498497c80e0"
}
```

{% hint style="info" %}
The networks of some coins like `XRP` and `XLM` are extremely fast. It takes literally ~1 second to verify and confirm a transaction once it is broadcast on the network. 
{% endhint %}

{% hint style="info" %}
On average a Bitcoin transaction to be included in a block requires ~15 minutes. By using Finrax you'll be able to credit Bitcoin deposits in less than 10 seconds.
{% endhint %}



