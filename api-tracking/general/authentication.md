# Authentication

To obtain your API ID for use with the 8SELECT API Tracking, please speak to your account manager.‌

Your API ID is permanently linked to your 8SELECT account. It must be included in every call to the tracking API as a `x-api-id` header to authorize your request:

```bash
POST /analytics/v3/events
Host: https://api.8select.io
x-api-id: <Your API ID>
```
