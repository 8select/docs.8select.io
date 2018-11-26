# Overview

Prerequisite for filling the widgets with content is the delivery of the online shop product data to a standard interface provided by 8select. Product data have to be uploaded regularly in an appropriate CSV format on an AWS S3 bucket provided by 8select.

There are two types of delivery:

* Master Data Feed: All products with all requested attributes as well as image URLs - 1x delivery daily.
* Update-Feed: Current values ​​for price, availability and selected product attributes as well as images - delivery every X minutes and if possible only one delta.

## Format

* Product variants are only allowed to be based on size, everything else e.g. colors must be transferred to virtual parent products.
* The export contains product variants only. Parent products and possibly virtual parent products are only needed for grouping variants via `mastersku` and`model`.
* If there are multiple properties that define sizes, then these have to be regarded in the export \(size, length, content \).
* If none of the properties specify the size of the item or the item as a universal size, then you have to export the property `groesse` with the value `onesize`.
* Separate multiple entries in one field with pipe `|`, do not insert extra spaces - e.g. for a multicolored shirt: Farbe `black | red | gold`
* CSV separator: semicolon `;`
* CSV-Text-Qualifier: double quotes `"`

### Example-Export

## AWS S3

* Upload to S3 Bucket
* Upload takes place with credentials
* ACL of the file must be set to bucket-owner-full-control
* Bucket: s3://productfeed.8select.io/

### File path

```text
<bucket>/<feed_id>/<feed_type>/<year>/<month>/<day>/<feed_id>_<feed_type>_<timestamp>.csv
```

* feed\_id = field “Feed ID” from Plugin Configuration
* feed\_type
  * daily master data export = product\_feed
  * Price, statusupdates and updates of selected attributes as well as Images = property\_feed
* year = current year in format yyyy - z.B. 2018 \(UTC\)
* month = current month in format mm - z.B. 05 \(UTC\)
* day = current day in format dd - z.B. 07 \(UTC\)
* timestamp = unix timestamp in millisecondd - e.g. 1515147815000 \(UTC\)

