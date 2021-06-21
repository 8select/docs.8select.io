# User Identification

To enable commission based pricing the user has to be identified with a consistent identifier. The identifier is wrapped in a context object and must be consistent for all events concerning a single user:

```javascript
{
  ...

  "context": [
		{ 
		  "type": "user",
		  "user": {
		    "id": "c57a43f7-eefc-462b-b5a8-0ef421e90f67"
		  }
		}
	],
	
	...
}
```

The identifier should be anonymized, i.e. a generated id without any connection to personal data.  
This has to be done on a best efforts basis. We know that making this work 100% of the time is impossible because users can clear their device cache or change devices or something else to break the consistency.

