# Withdrawal broadcast notification

Currently, we support 20+ cryptocurrencies as a payout option. Once you initiate a withdrawal we need to take care of a couple of things before we successfully broadcast it to the network. Withdrawals take on average 10 minutes to be broadcast on the designated blockchain network. Upon completion, you'll receive a callback notification.

> This callback notification is sent on your `withdrawalCallbackUrl` endpoint.

{% tabs %}
{% tab title="Success" %}
```javascript
{
    "status": "COMPLETED",
    "clientWithdrawalId": "Example-Withdrawal",
    "businessId": "19dee3c4-4dc9-4bcc-b8ed-92e3d4f256bd",
    "withdrawalId": "9b479a98-99ed-4bf9-87e0-4a05dbb012b6",
    "displayCurrency": "TRY",
    "withdrawCurrency": "XRP",
    "settlementCurrency": "USDT",
    "expectedDisplayAmount": "200.00000000",
    "actualDisplayAmount": "200.00000000",
    "estimatedWithdrawAmount": "119.63196400",
    "actualWithdrawAmount": "119.66467800",
    "deductedSettlementAmount": "35.28559158",
    "withdrawFee": "0.25000000",
    "displayFee": "0.42000000",
    "toTxAddress": "rLsVuk4hgmGUtjQKj1ybpg1etnFodZ4CJ?dt=140",
    "transactionId": "1AABB14A963442246EC6252B6FDCC72223544B9BBB9E28C431DF2F1C B3545DB5"
}
```
{% endtab %}

{% tab title="Failure" %}
```javascript
{
    "status": "FAILED",
    "clientWithdrawalId": "Example-Withdrawal",
    "withdrawalId": "9b479a98-99ed-4bf9-87e0-4a05dbb012b6",
    "reason": "Unprocessable transaction"
}
```
{% endtab %}
{% endtabs %}



### Schema

| Parameter                 | Type   | Description                                                                                                                         |
| ------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| status                    | number | One of`COMPLETED` or `FAILED`                                                                                                       |
| actualWithdrawAmount      | number | Actual amount withdrawn in `withdrawCurrency`Can be different than `estimatedWithdrawAmount`                                        |
| actualDisplayAmount       | number | Actual amount withdrawn in `displayCurrency` currency (e.g.`EUR, USD, GBP, TRY etc..)`Can be different than `expectedDisplayAmount` |
| clientWithdrawalId        | string | Unique withdrawal identifier provided by the merchant in the request body of POST `/withdrawals`                                    |
| withdrawCurrency          | string | Cryptocurrency to be withdrawn                                                                                                      |
| deducedSettlementCurrency | number | Amount debited from the merchant's balance in `settlementCurrency`                                                                  |
| settlementCurrency        | string | The currency in which the merchant's account was debited because of the withdrawal (can be either fiat or cryptocurrency)           |
| displayFee                | number | Blockchain cost for this withdrawal in `displayCurrency`                                                                            |
| withdrawFee               | number | Blockchain cost for this withdrawal in `withdrawCurrency`                                                                           |
| toTxAddress               | string | The address to which the `actualWithdrawAmount`was sent                                                                             |
| transactionId             | string | Unique blockchain transaction ID of the withdrawal                                                                                  |
| displayCurrency           | string | The fiat currency chosen for display (denomination) purposes                                                                        |
| expectedDisplayAmount     | number | Amount in `displayCurrency `requested for this payment                                                                              |
| estimatedWithdrawAmount   | number | Estimated amount for this withdrawal. Can be different than `actualWithdrawAmount`                                                  |
| withdrawalId              | string | Unique Finrax withdrawal identifier `UUID`                                                                                          |
| businessId                | string | Unique Finrax business identifier `UUID`                                                                                            |
