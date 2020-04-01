# Withdrawal broadcast time

Currently we support 50+ cryptocurrencies as a payout option. Once you initiate a withdrawal we need to take care of couple of things before we successfully broadcast it to the network.

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



