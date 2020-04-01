# Callbacks



Finrax sends 4 types of callback notifications on your predefined endpoints of your business. This is a high-level overview on how and when you can use the callback notifications

*  `depositReceivedCallbackUrl` Receives callback at deposit broadcast and received time \(e.g. once the transaction is broadcast on the blockchain and at 1 blockchain confirmation\)
*  `depositExchangedCallbackUrl` Receives callback at deposit exchanged time \(The time at which the deposit got exchanged into your desired settlement currency\)
* `withdrawalCallbackUrl`Callback sent when a withdrawal is successfully broadcast on the blockchain

![Callback requests timeline](../../.gitbook/assets/macbook-pro-1%20%281%29.png)

{% hint style="success" %}
Handling callbacks plays significant role for smooth service operations. The purpose is to allow easy, fast and automated reconciliation with your systems to properly assign Deposits and Withdrawals of your users.
{% endhint %}

{% hint style="success" %}
 For fair end-user experience, compare the `expectedDepositAmount` with `actualDepositAmount`IF equal we suggest assigning the `expectedDisplayAmount`  
This way the end-user will receive the full value that he expected on his account. The difference between `actualDisplayAmount` and `expectedDisplayAmount`is ****considered **fxGainLoss** which will be reported accordingly. In the long run the value of **fxGainLoss** should be neutralized.
{% endhint %}

{% hint style="info" %}
 For coins which have longer processing time, we send two callback notifications on `depositReceivedCallbackUrl` endpoint. This allows the merchant to credit the deposit of the user, while still in **`UNCONFIRMED`** status. We suggest putting a threshold on the maximum allowance.
{% endhint %}

