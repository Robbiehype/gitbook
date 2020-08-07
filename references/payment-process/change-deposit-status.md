# Change deposit status 🔒

![](../../.gitbook/assets/component-86.png)

{% api-method method="patch" host="https://payments.finrax.com" path="/api/v1/payments/:id/status" %}
{% api-method-summary %}
Change payment status
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to change the status of a payment request. Works well if you are using our UI and you would like to update the payment page. We suggest using it together with the callback notification at **`Deposit broadcast time`**If you want to approve deposits while still in `UNCONFIRMED` status, you can also use this endpoint to change the status to `PROCESSED` so we can update the UI from "Awaiting" to "Confirmed".
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Unique Finrax payment ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="status" type="string" required=true %}
Could be `PROCESSED`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Payment status changed successfully
{% endapi-method-response-example-description %}

```javascript
{
  "paymentId": "6d2a9979-ca29-46a5-a1c4-9dbf74e58000",
  "status": "PROCESSED"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% hint style="info" %}
### What will happen if I don't change the status?

It's not a critical resource. The idea is simple - If you are using our checkout page there's no way for us to know if you are crediting your end-users on`UNCONFIRMED` or `CONFIRMED` callback notification. In other words, we'll display to the user that we are awaiting blockchain confirmation, unless we are told otherwise by **you.**

* If you are going to use the callback notification with `UNCONFIRMED` status you might want to update the status.
* If you are using the callback notification with `CONFIRMED` status, then you can skip this request.
{% endhint %}

\*\*\*\*

