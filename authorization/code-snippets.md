---
description: Example code snippets fo signing and sending requests
---

# Code snippets

{% tabs %}
{% tab title="PHP" %}
```php
class Finrax
{
    private $apiKey;
    private $apiSecret;
    private $baseUrl = 'https://sandbox-payments.finrax.com';
    
    
    public function __construct(string $apiKey, string $apiSecret)
    {
        $this->apiKey = $apiKey;
        $this->apiSecret = $apiSecret;
    }
    
    public function makeRequest($method, $endpoint, array $body = [], array $query = [])
    {
        $method = strtoupper($method);
        $qs = http_build_query($query, '', '&');
        $path = ($qs == '') ? $endpoint : $endpoint . '?' . $qs;
        $ch = curl_init();
        $jsonBody = '';
        if ($method == 'POST' || $method == 'PUT' || $method == 'PATCH') {
            $jsonBody = json_encode($body, JSON_UNESCAPED_SLASHES);
            curl_setopt($ch, CURLOPT_POSTFIELDS, $jsonBody);
        }
        curl_setopt_array($ch, [
            CURLOPT_URL => $this->baseUrl . $path,
            CURLOPT_CUSTOMREQUEST => $method,
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_HTTPHEADER => [
                'Content-Type: application/json',
                'Authorization: ' . $this->buildAuthorizationHeaderValue($path, $jsonBody)
            ]
        ]);
        $response = curl_exec($ch);
        curl_close($ch);
        return json_decode($response, true);
    }
    
    private function buildAuthorizationHeaderValue($path, $jsonBody = '') 
    {
        $timestamp = intval(microtime(true) * 1000);
        $signaturePayload = $path . $timestamp . $jsonBody;
        $signature = hash_hmac('sha256', $signaturePayload, $this->apiSecret);
        return "FRX-API API-Key={$this->apiKey}," .
               "Signature={$signature}," .
               "Timestamp={$timestamp}";
    }
}
```
{% endtab %}

{% tab title="JS" %}
```javascript
'use strict';
const CryptoJS = require('crypto-js');
const fetch = require('node-fetch');
const Headers = fetch.Headers;
const API_KEY = process.env.API_KEY;
const API_SECRET = process.env.API_SECRET;
const BASE_URL = process.env.BASE_URL || 'https://sandbox-payments.finrax.com';

function buildAuthorizationHeaderValue(path, jsonBody = '') {
    let timestamp = Date.now();
    let signaturePayload = path + timestamp + jsonBody;
    let signature = CryptoJS.HmacSHA256(signaturePayload, API_SECRET);
    
    return `FRX-API API-Key=${API_KEY},` +
        `Signature=${signature},` +
        `Timestamp=${timestamp}`;
}

function stringifyBody(jsonBody) {
    if (typeof jsonBody === 'string') {
        if (jsonBody === '') {
            throw "Body is requried for POST, PATCH, PUT requests.";
        }
        jsonBody = JSON.stringify(JSON.parse(jsonBody));
    } else {
        jsonBody = JSON.stringify(jsonBody);
    }
    
    return jsonBody;
}

function buildRequestOptions(method, path, jsonBody) {
    let requestOptions = {};
    let body = '';
    if (method === 'POST' || method === 'PUT' || method === 'PATCH') {
        body = stringifyBody(jsonBody);
        requestOptions.body = body;
    }
    
    let authorizatonHeader = buildAuthorizationHeaderValue(path, body);
    let headers = new Headers();
    headers.append('Authorization', authorizatonHeader);
    headers.append('Content-type', 'application/json');
    requestOptions.method = method;
    requestOptions.headers = headers;
    
    return requestOptions;
}

function makeRequest(method, path, jsonBody = '') {
    let url = BASE_URL + path;
    let requestOptions = buildRequestOptions(method, path, jsonBody);
    
    fetch(url, requestOptions)
        .then(response => response.text())
        .then(result => console.log(result))
        .catch(error => console.log('error', error));
}
```
{% endtab %}
{% endtabs %}
