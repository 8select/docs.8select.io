# Introduction

## How to send events?

The analytics API is built using REST. To submit an event you send a POST request to `https://api.8select.io/analytics/v3/events`:

```bash
POST /analytics/v3/events
Host: https://api.8select.io
Content-Type: application/json
x-api-id: <Your API ID>

{ 
	"userId": "c57a43f7-eefc-462b-b5a8-0ef421e90f67",

	"type": "view",

	"view": {
		"type": "setCompose",
		"setCompose": {
			"id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
		},
	},

	"context": [
		{ "type": "api" }
	]
}
```

Every event has to contain a type, a context and a type-specific payload. To enable commission based pricing a userId is required as well.

### userId

The `userId` must be consistent for all events concerning a single user. It should be anonymised, i.e. a generated id without any connection to personal data. You can read the section about [user identification](user-identification.md) to learn more.

### type

There are currently three types of events \(view, interact, order\), each with a specific payload as defined in the respective sections under [events](../events/).  
The property containing the type specific payload is always named after the type itself.

### context

The context is used to provide additional contextual information about the origin of a given event. You can read the section about [context](context.md) to learn more.

