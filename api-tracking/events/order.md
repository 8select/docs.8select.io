# order

An order event should be triggered whenever a user, i.e. one of your customers, places an order. It should look like the following example.

{% hint style="warning" %}
Make sure you send the amount that 1 item costs as `amount` and not the sum of the order line.
{% endhint %}

```javascript
{
  "type": "order",
  "order": {
    "id": "0987654321", // either your original id or a pseudonymized value - i.e. same input always produces same anonymous output
    "lines": [
      {
        "sku": "654321-7890",
        "grossPrice": {
          "amount": 0.99, // unit price - i.e. price of 1 item not the sum of 5
          "currency": "EUR" // currency code as defined by ISO 4217
        },
        "quantity": 5 // how many items where bought
      },
      {
        "sku": "567890-4321",
        "grossPrice": {
          "amount": 49.95,
          "currency": "EUR"
        },
        "quantity": 1
      }
    ]
  },
  "context": [
    {
      "type": "user",
      "user": {
        "id": "c57a43f7-eefc-462b-b5a8-0ef421e90f67"
      }
    }
  ]
}
```

The context array must currently always contain an object with type `user` as defined in the [context](../general/context.md) section and the user ID specified therein must be a consistent identifier as described in the [user identification](../general/user-identification.md) section.&#x20;

An order event is identified by its type `order` and an additional `order` property containing specific information about the products being ordered. This property must have the `id` of the order in your shop system and a `lines` property, containing a list of ordered items.

Each order lines entry must contain the `sku` of the ordered product and the quantity of items ordered of this product. Additionally, it must include a `grossPrice` object with a `currency` code, as defined by [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217), and the `amount` of money paid (including e.g. VAT) for **one unit** of this entry, i.e. the price of a single item.

Lastly, the `context` must contain an object with type `user` as described in the [context](../general/context.md) section.

{% hint style="info" %}
Duplicate `order` events will be deduplicated using the `order.id` - you do not have to implement anything to prevent sending the order tracking event of an order multiple times.

But you need to make sure, that the `order.id` is always the same for the same order - i.e. use a determinstic approach to anonymize the `id` in case you do not send the original value.

Best would be to use an HMAC hash - for example SHA-256.
{% endhint %}

### example for order.id pseudonymization

{% tabs %}
{% tab title="JavaScript" %}
```javascript
const crypto = require('crypto');

/**
 * Anonymizes an Order ID deterministically.
 * @param {string} orderId - The original order ID.
 * @param {string} secretKey - A private key known only to your system.
 * @returns {string} - A consistent hex-encoded hash.
 */
function anonymizeOrderId(orderId, secretKey) {
  return crypto
    .createHmac('sha256', secretKey)
    .update(orderId)
    .digest('hex');
}

// Example Usage:
const mySecret = 'super-secret-pepper-key-123';
const originalId = 'ORD-99502';

const anonymizedId1 = anonymizeOrderId(originalId, mySecret);
const anonymizedId2 = anonymizeOrderId(originalId, mySecret);

console.log(`Original: ${originalId}`);
console.log(`Anonymized 1: ${anonymizedId1}`);
console.log(`Anonymized 2: ${anonymizedId2}`);

// Verification
console.log('Match:', anonymizedId1 === anonymizedId2);
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php

/**
 * Anonymizes an Order ID deterministically.
 * * @param string $orderId   The original order ID.
 * @param string $secretKey A private key stored securely (e.g., in .env).
 * @return string           A consistent hex-encoded hash.
 */
function anonymizeOrderId(string $orderId, string $secretKey): string {
    // We use sha256 for a good balance of security and performance
    return hash_hmac('sha256', $orderId, $secretKey);
}

// Example Usage:
$mySecret = 'your-secure-system-key-here';
$originalId = 'ORD-99502';

$anonymized1 = anonymizeOrderId($originalId, $mySecret);
$anonymized2 = anonymizeOrderId($originalId, $mySecret);

echo "Original: " . $originalId . PHP_EOL;
echo "Anonymized 1: " . $anonymized1 . PHP_EOL;
echo "Anonymized 2: " . $anonymized2 . PHP_EOL;

if ($anonymized1 === $anonymized2) {
    echo "Success: The values are consistently mapped.";
}
```
{% endtab %}
{% endtabs %}
