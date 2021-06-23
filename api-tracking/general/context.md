# Context

As implied by its name the context is supposed to provide contextual information about an event. This will help to classify and interpret KPIs generated from the events. Put differently the context describes the user journey from the inside out. This can range from the specifics of single elements in a product set to global information such as the containing page or even enduser navigating the pages. Some of this contextual data will be attached at the API level. Other information has to be supplied from the client-side.

```javascript
{
  ...,
	"context": [
		{
			"type": "setCompose",
			"setCompose": {
				"id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
			},
		},
		{ "type": "api" }
	]
}
```

Similarly to the event structure itself, `context` elements will always have a `type` and optionally a type-specific payload named thereafter. 

{% hint style="info" %}
Currently, only two context types are supported: `setCompose` and `user`.
{% endhint %}

## user

{% hint style="danger" %}
**Required**: Every event _must_ contain a context item with type `user`. Please read the [user identification](user-identification.md) section to learn more about the technical specifics of this context.
{% endhint %}

If you are using commision-based pricing, the `user` context is responsible for the event attribution:

```javascript
{ 
  "type": "user",
  "user": {
    "id": "<user-id>"
  }
}
```

Read the section about [user identification](user-identification.md) for more information on commision-based pricing and the requirements for the anonymized user ID.

## setCompose

If the tracked interaction takes place within the context of an 8.SET Compose product set, e.g. a click on one of the products in the set, the following information must be included in the context of this event:

```javascript
{
  "type": "setCompose",
  "setCompose": {
    "id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
  },
}
```

