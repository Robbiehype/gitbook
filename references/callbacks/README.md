# Callbacks



Finrax sends 2 types of callback notifications on your predefined endpoints that you can set when creating [your business](https://blog.finrax.com/guides/how-to-create-a-business). This is a high-level overview of how and when you can use the callback notifications

* `depositReceivedCallbackUrl` Receives callback when the deposit has been seen (broadcasted) on the blockchain, or when the deposit has been confirmed on the blockchain.
* `withdrawalCallbackUrl` Receives a callback when a withdrawal transaction was successfully broadcasted on the blockchain

![](<../../.gitbook/assets/Callbacks timeline.png>)

### Signature

Finrax sends every callback notification with Signature and Timestamp components in the request headers. This allows you to verify that each notification was sent by Finrax, and not by a third party.

Finrax generates signatures using RSA with SHA-512 and encodes the result with BASE64. The following function generates the signature: `Base64(RSA(PRIVATE_KEY, SHA512(requestBody.timestamp)))` Finrax uses a unique private key for each environment, so please note to use the correct public key for Sandbox and Production, for more information please visit [Environments](../../environments.md).

The procedure for verifying a signature is as follows:

**Step 1**. Extract the values from the Signature and Timestamp headers.

**Step 2.** Prepare the payload string by concatenating the actual JSON payload (i.e., the request body), the character \`.\`, and the timestamp.

**Step 3**. Using the appropriate public key and your favorite cryptography library, you can ensure that the signatures match.\
\
Here's an example snippet in JS:

```javascript
const crypto = require("crypto");
const signature = ...;
const publicKey = ...;
const requestBody = ...;
const timestamp = ...;
const signaturePayload = `${requestBody}.${timestamp}`;
const verifier = crypto.createVerify('RSA-SHA512');
verifier.write(signaturePayload);
verifier.end();
const isVerified = verifier.verify(publicKey, signature, "base64");
console.log("Verified:", isVerified);
```



{% hint style="success" %}
Handling callbacks plays a significant role for smooth service operations. The purpose is to allow easy, fast and automated reconciliation with your systems to properly assign Deposits and Withdrawals of your users.\

{% endhint %}

{% hint style="info" %}
For coins which have longer processing time, we have [instant deposit](https://blog.finrax.com/guides/instant-deposits) functionality. \
This allows the merchant to credit users' deposits, while transfers are still _confirming_ on the blockchain. 
{% endhint %}
