# Legacy

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/c70d4675a0210919969a#?env%5BFinrax%20Postman%20Legacy%5D=W3sia2V5IjoiaG9zdCIsInZhbHVlIjoiaHR0cHM6Ly9wYXltZW50cy5maW5yYXguY29tIiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJidXNpbmVzc1Rva2VuIiwidmFsdWUiOiJ5b3VyX2J1c2luZXNzX3Rva2VuIiwiZW5hYmxlZCI6dHJ1ZX1d) 👈Legacy version with businessToken 

For legacy integrators Finrax uses the **Authorization bearer** schema for request authentication. In order to start making requests to the API you must first create a business in the Finrax Dashboard. You'll be supplied with a **businessToken** in [JWT](https://jwt.io) standard.

![](../.gitbook/assets/screenshot-2020-03-19-at-13.34.48.png)

{% hint style="danger" %}
**Finrax will continue to support the legacy authentication schema until 1st of June 2020.**
{% endhint %}

{% hint style="warning" %}
**Currently, authenticated endpoints supporting the legacy schema are:**

[**Initiate deposit request**](../references/payment-process/initiate-a-deposit-request.md)\*\*\*\*

\*\*\*\*[**Submit deposit data**](../references/payment-process/submit-deposit-data.md)\*\*\*\*

[**Initiate withdrawal request**](../references/payment-process/initiate-withdrawal-request.md)\*\*\*\*

\*\*\*\*[**Get deposit data**](../references/payment-process/get-deposit-data.md)\*\*\*\*

\*\*\*\*[**Get business by ID**](../references/business/get-business-by-id.md)
{% endhint %}



