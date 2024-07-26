# Changelog

## [2.0.0 - 2024-07-25](2.0.0.md)

### Implemented Features

* You can now request any type of content via the API
* The schema completely changed
* You can now not only get the product id but also the properties like brand, name, prices etc.
  * To ensure that you show the most recent data you should still make an extra roundtrip to your own database and fetch the most recent data to render your UI

[Go to detailed version description.](2.0.0.md)

## [1.0.1 - 2021-04-27](1.0.1.md)

### Fixed Bugs

* An empty result is now empty, before it contained an edge with `null` values

[Go to detailed version description.](1.0.1.md)

## 1.0.0 - 2021-03-12

### Implemented Features

* Initial release with support for 8.SET Compose

