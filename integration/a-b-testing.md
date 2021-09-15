---
description: We ❤️ data driven
---

# A/B Testing

Like us, many clients also follow the approach of "Data Driven Development". A/B tests are essential for this.   
In order for our platform to be able to generate reliable KPIs, it is important that widgets used in an A/B test are not simply hidden \(**display:none**\), but are not integrated in the DOM at all. 

This is not always so easy to do, but it is essential to get a reliable data basis. Just contact us and we will find a solution together!

##  General Info

## Sync your and our A/B test

In order to sync the A/B test variant \(or test group\) allocation from your shop and our solution you can just add it to the 8.SDK Web configuration.

```javascript
// 8.SDK Web
<script type="text/javascript">
    ...
</script>


// 8.SDK Web configuration for Shop's A/B test test group
<script type="text/javascript">
  window._eightselect_shop_plugin = window._eightselect_shop_plugin || {};
  window._eightselect_shop_plugin.testgroup = 'A'; // set to whatever value you use to identify your test group or variant
</script>
```



