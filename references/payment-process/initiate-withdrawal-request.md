# Initiate withdrawal request 🔒

{% api-method method="post" host="https://payments.finrax.com" path="/api/v1/withdrawals" %}
{% api-method-summary %}
Initiate withdrawal request
{% endapi-method-summary %}

{% api-method-description %}
An endpoint for initiating cryptocurrency withdrawals. The amount can be selected either in `fiat` or `crypto` which is being defined by the `targetAmountPolicy`
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="businessId" type="string" required=true %}
ID of the business from which the withdrawal should be executed. **Optional for businessToken**
{% endapi-method-parameter %}

{% api-method-parameter name="clientWithdrawalId" type="string" required=true %}
Withdrawal identifier provided by you
{% endapi-method-parameter %}

{% api-method-parameter name="recipientAddress" type="string" required=true %}
Wallet address of the recipient
{% endapi-method-parameter %}

{% api-method-parameter name="withdrawCurrency" type="string" required=true %}
Cryptocurrency abbreviation that should be withdrawn e.g. `BTC`  `ETH`  `XRP`
{% endapi-method-parameter %}

{% api-method-parameter name="displayCurrency" type="string" required=true %}
Fiat currency abbreviation for pairing e.g. `USD`  `EUR`  `GBP`
{% endapi-method-parameter %}

{% api-method-parameter name="targetAmountPolicy" type="string" required=true %}
Specifies if the `targetAmount` will be requested in `fiat` or `crypto`
{% endapi-method-parameter %}

{% api-method-parameter name="targetAmount" type="string" required=true %}
The requested amount to be withdrawn in `fiat` or `crypto`
{% endapi-method-parameter %}

{% api-method-parameter name="destinationTag" type="string" required=false %}
Applicable for `XRP` and `XLM` If no `destinationTag` is needed `0` should be entered
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Withdrawal request created successfully
{% endapi-method-response-example-description %}

```javascript
{
  "withdrawId": "b4c16bbc-d192-4cd1-ae95-e23ca12cbf1c",
  "clientWithdrawId": "My first Withdrawal",
  "recipientAddress": "rLsVuk4hgmGUtjQKj1ybpg1etnFodZ4CJ?dt=140",
  "initiatedBy": "http://gateway.finrax.test",
  "status": "NEW",
  "displayCurrency": "TRY",
  "withdrawCurrency": "XRP",
  "settlementCurrency": "USDT",
  "estimatedDisplayAmount": "200.00",
  "estimatedWithdrawAmount": "112.053789",
  "settlementDeductedAmount": "35.45448769",
  "createdAt": 1568882280
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% hint style="info" %}
### What is `targetAmountPolicy?`

The `targetAmountPolicy`field provides the means for specifying the withdrawal amount either in `FIAT` currency or `CRYPTO` currency. When `FIAT` is selected as policy the resulting amount of the withdrawal in crypto will be calculated according to the fiat amount passed in `targetAmount` field. When `CRYPTO` is selected as policy the resulting amount of the withdrawal will be exactly the same as the amount passed in `targetAmount` field \(subject to a negligible difference due to market conditions i.e. market step size\)
{% endhint %}

```javascript
{
    'withdrawCurrency': 'XRP',
    'displayCurrency': 'EUR',
    'targetAmount': '20',
    'targetAmountPolicy': 'FIAT'
}

//This translates to "Withdraw 20 EUR worth of XRP"
```

```javascript
{
    'withdrawCurrency': 'XRP',
    'displayCurrency': 'EUR',
    'targetAmount': '200',
    'targetAmountPolicy': 'CRYPTO'
}

//This translates to "Withdraw 200 XRP"
```



