# Introduction

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/5841bba39f95dc621792#?env%5BFinrax%20Postman%20collection%5D=W3sia2V5IjoiaG9zdCIsInZhbHVlIjoiaHR0cHM6Ly9wYXltZW50cy5maW5yYXguY29tIiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJzYW5kYm94LWhvc3QiLCJ2YWx1ZSI6Imh0dHBzOi8vc2FuZGJveC1wYXltZW50cy5maW5yYXguY29tIiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJhdXRob3JpemF0aW9uVmFsdWVzIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlfSx7ImtleSI6IlgtQVBJLUtleSIsInZhbHVlIjoieW91cl9hcGlfa2V5IiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJYLUFQSS1TZWNyZXQiLCJ2YWx1ZSI6InlvdXJfYXBpX3NlY3JldCIsImVuYWJsZWQiOnRydWV9XQ==)

Finrax Payment Gateway is a solution which enables merchants to accept cryptocurrency payments and initiate withdrawals to customers at ideal exchange rates. The following API documentation comprise of all currently supported public endpoints. Each separate endpoint is accompanied by a small description together with a few example requests and responses.

[HTTP response status codes](https://www.restapitutorial.com/httpstatuscodes.html) indicate whether a specific request has been successfully completed or resulted in a failure

All timestamps are formatted in [UNIX](https://www.unixtimestamp.com/)

{% hint style="warning" %}
We've switched to a new Authorization schema, which allows better control and security around our REST API. It is backward compatible with the [Legacy](authorization/legacy.md) integrations, however we highly advise you to switch over to the new Authorization mechanism. The businessToken will be deprecated as of 1st of June 2020.

If you require additional assistance with the API credentials please contact us at **info@finrax.com.**

Feel free to check the [code snippets ](authorization/code-snippets.md)for your convenience.
{% endhint %}

