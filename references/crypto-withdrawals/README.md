# Crypto withdrawals

In this section we'll go through the endpoints you'll need to execute crypto withdrawals.

By utilizing this functionality, you will be able to send payouts to your customers in cryptocurrencies without prior holding it, thus we remove the crypto volatility and complexity.

The Crypto withdrawals work on a Buy&Send basis. The moment you initiate the withdrawal request, we'll purchase the given cryptocurrency on a [mid-market rate](https://blog.finrax.com/articles/why-is-your-crypto-payment-processing-not-working) and send it immediately to your customer.  
In addition we allow you to specify the amount in fiat currency to denominate the amount in a currency you are used to and only specify the cryptocurrency you wish to send.

{% hint style="warning" %}
Bear in mind that we don't cover on-chain fees for withdrawals. Please make sure to get familiarised with the on-chain fees per currency, before executing a withdrawal.  
The on-chain fees are deducted from the selected amount in the withdrawal request i.e. if you wish to withdraw 1 Litecoin,  the recipient will receive 1 Litecoin minus the associated on-chain fee. List of current on-chain fees [here](https://finrax.com/onchain-fees).
{% endhint %}

### Withdrawal statuses

| Status | Description |
| :--- | :--- |
| NEW | We've received your Withdrawal request and it has passed our initial validations. |
| PENDING | The withdrawal request has passed the required steps i.e. we've bought the requested cryptocurrency and have deducted your balance. The transaction is to be broadcast on the blockchain network. |
| COMPLETED | The blockchain transaction has been validated on the blockchain, thus the recipient should have access to the funds. A [callback notification](../callbacks/) will be sent to your designated endpoint. |
| FAILED | The withdrawal request has failed. We'll trigger a callback notification with a failure status and description. |



