# Dead Products / Change of SKU

As most shops are unable to send a delta export (only data that changed) the most common use case for a data export is that we get a file with all active (buyable) products of a shop. Therefore we can not distinguish between products that are out of stock and products that are not in the shop anymore. This normally is not a problem but there are rare occasions when this will become one.

### Change of product identifiers - SKU

In case the product identifier (SKU) is changed while the main SKU still remains the same we will end up with variants using the old SKU and variants using the new SKU combined under the same product. In those cases it is necessary to tell us which products are updated so we can react accordingly. Otherwise we may show outdated data in our widgets.

#### Example

Jean "James"

old SKU schema: `jeans-james-<size>` e.g. `jeans-james-34-34`

new SKU schema: EAN e.g. `9781234567897`
