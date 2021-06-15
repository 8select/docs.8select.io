# Events

For the time being we only support a limited amount of KPIs and therefor only a limited amount of events is required if you want to use those KPIs.

Currently there are three types of events: `view`, `interact` and `order`.

### [view](view/)

Whenever the user has seen some 8SELECT content, i.e. it was in the device's viewport. For example if an 8.SET Compose content is presented to the user.

### [interact](interact.md)

Whenever the user has interacted with 8SELECT content. For example clicked on a product.

Interact events and order events from users are matched and are the base of the commission based pricing. If user A interacts with content from 8.API, e.g. product 42 and later buys product 42, 8SELECT will get a commission.

### [order](order.md)

Whenever the user makes an order.

