# Context

As implied by its name the context is supposed to provide contextual information about an event. This will help to classify and interpret KPIs generated from the events. Put differently the context describes the user journey from the inside out. This can range from the specifics of single elements in a product set to global information such as the containing page. Some of this contextual data will be attached at the API level. Other information has to be supplied from the client-side.

```text
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
Currently, only two pieces of context are supported: `api` and `setCompose`.
{% endhint %}

## api

If you are using [8.API](../../api/8.set-compose/) to fetch product set data, you must include the following context in your events:

```text
{ "type": "api" }
```

## setCompose

If the tracked interaction takes place within the context of an 8.SET Compose product set, e.g. a click on one of the products in the set, the following information must be inlcuded in the context of this event:

```text
{
  "type": "setCompose",
  "setCompose": {
    "id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
  },
}
```

