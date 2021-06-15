# Context

* api
* setcompose
* what does it do
* there will be more

As implied by its name the context is supposed to provide contextual information about an event. This will help to classify and interpret KPIs generated from the events. Put differently the context describes the user journey from the inside out.

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

