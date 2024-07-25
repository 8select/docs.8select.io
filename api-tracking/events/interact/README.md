# interact

An interact event should be triggered whenever a piece of content is interacted with by a user. Assuming that you are showing 8.SET product set data and a user clicks on a product contained in that set, the event should look like the following example:

```javascript
{
  "type": "interact",
  "interact": {
    "action": "click",
    "type": "product",
    "product": {
      "sku": "654321-7890"
    }
  },
  "context": [
    {
      "content": {
        "matchingProductClusters": {
          "id": "457297-0001-00340"
        },
        "type": "matchingProductClusters"
      },
      "type": "content"
    },
    {
      "type": "user",
      "user": {
        "id": "c57a43f7-eefc-462b-b5a8-0ef421e90f67"
      }
    }
  ]
}
```

The context array must currently always contain an object with type `user` as defined in the [context](../../general/context.md) section and the user ID specified therein must be a consistent identifier as described in the [user identification](../../general/user-identification.md) section.&#x20;

An interact event is identified by its type `interact` and an additional `interact` property containing specific information about the content being interacted with. This property should in turn have a type and content-specific payload, as well as an optional third property `action` specifying the user interaction, e.g. `click` or `addToCart`.

{% hint style="info" %}
Currently, only `product` interactions are taken into consideration.
{% endhint %}

## product

An interact event with type `product` must contain a `product` property containing the `sku` of the respective product and can contain an `action`.

Some example actions: `click`, `addToCart`, `navigateTo`, `addToWishlist`, `like`, `share`.

```javascript
{ 
  ...,
  "interact": {
    "action": "click",
    "type": "product",
    "product": {
      "sku": "654321-7890"
    }
  },
  ...
}
```

While an arbitrary `action` can be supplied we currently only have KPIs that differentiate between `addToCart` and any other action.&#x20;

{% hint style="info" %}
If you are not sure how to name the `action` simply omit the property.
{% endhint %}
