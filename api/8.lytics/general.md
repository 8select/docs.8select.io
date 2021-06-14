# General

## User identification

To enable commission based pricing the user has to be identified with a consistent identifier. The identifier called `userId` needs to be consistent for at least 90 days. I.e. when user A visits your shop on 04.05.2021 and comes back on 04.07.2021 the user has to have the same `userId` as on the first visit.  
This has to be done on a best efforts basis. We know that making this work 100% of the time is impossible because users can clear their device cache or change devices or something else to break the consistency.

## Type of events

For the time being we only support a limited amount of KPIs and therefor only a limited amount of events is required if you want to use those KPIs.

Currently there are three types of events: `view`, `interact` and `order`.

### view

Whenever the user has seen some 8SELECT content, i.e. it was in the device's viewport. For example if an 8.SET Compose content is presented to the user.

### interact

Whenever the user has interacted with 8SELECT content. For example clicked on a product.

Interact events and order events from users are matched and are the base of the commission based pricing. If user A interacts with content from 8.API, e.g. product 42 and later buys product 42, 8SELECT will get a commission.

### order

Whenever the user makes an order.

