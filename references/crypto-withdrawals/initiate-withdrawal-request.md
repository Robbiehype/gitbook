# 🔒 Request crypto withdrawal

{% swagger baseUrl="https://payments.finrax.com" path="/api/v1/withdrawals" method="post" summary="Initiate withdrawal request" %}
{% swagger-description %}
An endpoint for initiating cryptocurrency withdrawals. The amount can be selected either in 

`fiat`

 or 

`crypto`

 which is being defined by the 

`targetAmountPolicy`
{% endswagger-description %}

{% swagger-parameter in="body" name="businessId" type="string" %}
ID of the business from which the withdrawal should be executed. 

**Optional for businessToken**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientWithdrawalId" type="string" %}
Withdrawal identifier provided by you
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientAddress" type="string" %}
Wallet address of the recipient
{% endswagger-parameter %}

{% swagger-parameter in="body" name="withdrawCurrency" type="string" %}
Cryptocurrency abbreviation that should be withdrawn e.g. 

`BTC`

  

`ETH`

  

`XRP`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="displayCurrency" type="string" %}
Fiat currency abbreviation for pairing e.g. 

`USD`

  

`EUR`

  

`GBP`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="targetAmountPolicy" type="string" %}
Specifies if the 

`targetAmount`

 will be requested in 

`fiat`

 or 

`crypto`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="targetAmount" type="string" %}
The requested amount to be withdrawn in 

`fiat`

 or 

`crypto`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="destinationTag" type="string" %}
Applicable for 

`XRP`

 and 

`XLM`

 If no 

`destinationTag`

 is needed 

`0`

 should be entered
{% endswagger-parameter %}

{% swagger-response status="201" description="Withdrawal request created successfully" %}
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
{% endswagger-response %}
{% endswagger %}

{% hint style="success" %}
Please check our Withdrawal experience playground to help you create your checkout experience: [https://finrax.com/withdrawal-experience-playground](https://finrax.com/withdrawal-experience-playground)
{% endhint %}

{% hint style="info" %}
### What is `targetAmountPolicy?`

The `targetAmountPolicy`field provides the means for specifying the withdrawal amount either in `FIAT` currency or `CRYPTO` currency. When `FIAT` is selected as policy the resulting amount of the withdrawal in crypto will be calculated according to the fiat amount passed in `targetAmount` field. When `CRYPTO` is selected as policy the resulting amount of the withdrawal will be exactly the same as the amount passed in `targetAmount` field (subject to a negligible difference due to market conditions i.e. market step size)
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

