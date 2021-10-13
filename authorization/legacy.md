---
description: Legacy business token-based autorization scheme
---

# Legacy

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/c70d4675a0210919969a#?env%5BFinrax%20Postman%20Legacy%5D=W3sia2V5IjoiaG9zdCIsInZhbHVlIjoiaHR0cHM6Ly9wYXltZW50cy5maW5yYXguY29tIiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJidXNpbmVzc1Rva2VuIiwidmFsdWUiOiJ5b3VyX2J1c2luZXNzX3Rva2VuIiwiZW5hYmxlZCI6dHJ1ZX1d) 👈Legacy version with businessToken 

In order to start making requests to the API, you must first create a business in the Finrax Dashboard. You'll be supplied with a [JWT ](https://jwt.io)**businessToken**.

![](<../.gitbook/assets/Screenshot 2020-03-19 at 13.34.48.png>)

{% hint style="danger" %}
**Finrax will continue to support this legacy authentication scheme for a while but we plan to deprecate it in Q3 2020. New integrators are strongly advised to use the **[**API key & secret**](management.md)** instead.**
{% endhint %}

{% hint style="warning" %}
**Currently, authenticated endpoints supporting the legacy schema are:**

[**Initiate deposit request**](../references/crypto-payments/initiate-a-crypto-payment-request.md)****

****[**Submit deposit data**](../references/crypto-payments/submit-deposit-data.md)****

[**Initiate withdrawal request**](../references/crypto-withdrawals/initiate-withdrawal-request.md)****

****[**Get deposit data**](../references/crypto-payments/get-deposit-data.md)****

****[**Get business by ID**](../references/business/get-business-by-id.md)
{% endhint %}

