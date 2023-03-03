# Tag Manager

If you want to integrate 8SELECT via a tag manager like Google Tag Manager you can do this for the frontend part.\
But be aware that this will increase load times because the Tag Manager and the corresponding tag has to be loaded first.\
Moreover you have to have access to the necessary product data, e.g the [SKU](../product-export/base-data/) or [main-SKU](../product-export/base-data/) when on a product page and the SKU for the checkout tracking.\
You also have to be able to react to events like a user changing the active product variant, e.g. color in order to update our widget with the new product [SKU](../product-export/base-data/) or [main-SKU](../product-export/base-data/).
