# Deposit received notification

Once the end-user sends funds from their wallet, transaction-specific events will be broadcasted on the blockchain. We listen for such blockchain events and will send them to you via an endpoint provided by you when creating your business through the dashboard. There are two types of block-chain events that we propagate to you:  
  
The first event is sent as soon as we _see_ a new deposit transfer broadcasted on the designated wallet address. At this stage, the status of the transaction is still `UNCONFIRMED` We run an internal probabilistic algorithm to help us identify [double spent attempts](https://coinsutra.com/bitcoin-double-spending/) or illicit transactions. If we detect such a case we won't propagate this event to you systemically and will instead contact you about it. Note that only UTXO-based coins \(BTC, LTC, BCH etc..\) have such an event, whereas account-based coins \(ETH, ERC20, XLM, XRP\) don't.

The second type of event is sent once the transaction is added in a block and there is 1 blockchain confirmation, we trigger a callback notification on your registered endpoint with status `CONFIRMED` All coins support this event. 

> This callback notification is sent on your `depositReceivedCallbackUrl` endpoint.

```javascript
{
  "actualDepositAmount": 0.12547023,
  "actualDisplayAmount": 15,
  "clientPaymentId": "user_deposit_example_1",
  "depositAddress": "MHB8NrSJY8uYG1ra5mhzfqqU9ZyNw3L621",
  "depositCurrency": "LTC",
  "depositId": "67a8e476-fa11-354e-b958-801f3c37d011",
  "displayCurrency": "EUR",
  "displayServiceFee": 0.08,
  "expectedDepositAmount": 0.12547023,
  "expectedDisplayAmount": 15,
  "expirationTime": 1611580762,
  "onChainFee": 0.00000426,
  "paymentId": "9a601c2b-6cbc-48f9-8831-9ea57ab375f9",
  "paymentReceivedAt": 1611579024,
  "paymentRequestedAt": 1611578974,
  "rateType": "FIXED",
  "settlementAmount": 15,
  "settlementCurrency": "EUR",
  "settlementServiceFee": 0.08,
  "status": "CONFIRMED",
  "transactionId": "9d4ad57d39a7c38b6b909fd6adbff4979756ca352d6f03004f4cedd97641ded5"
}
```

{% hint style="info" %}
The networks of some coins like `XRP` and `XLM` are extremely fast. It takes literally ~1 second to verify and confirm a transaction once it is broadcast on the network. 
{% endhint %}

{% hint style="info" %}
On average a Bitcoin transaction to be included in a block requires ~15 minutes. By using Finrax you'll be able to credit Bitcoin deposits in less than 10 seconds.
{% endhint %}



