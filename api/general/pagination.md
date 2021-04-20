---
description: >-
  Whenever two objects have a one-to-many relationship, the respective field
  will be paginated using cursor-based, forward pagination.
---

# Pagination

{% hint style="warning" %}
As pagination is not yet fully implemented, all paginated fields will currently return **all** results. However, to avoid breaking changes once pagination will be enabled, the respective pattern is already prepared and enforced.
{% endhint %}

## Nodes and Edges

Objects that share a relationship within our API are referred to as **nodes** and their connections as **edges**. To enable pagination, a field representing a one-to-many relationship contains a single `edges` object, which in turn is a list of nodes. Each such `node` object represents a single related item.

According to this structure, you could query the title of all 8.SET Compose product sets for a product with the SKU `123456-7890` in your catalogue by using the follwing query:

```text
productSets(input: {queryType: SKU, value: "123456-7890"}) {
    edges {
        node {
            title
        }
    }
}
```

The responding result will reflect the same structure:

```text
{
    "data": {
        "productSets": {
            "edges": [
                {
                    "node" : {
                        "title": "Product Set Example 1"
                    }
                },
                {
                    "node" : {
                        "title": "Product Set Example 2"
                    }
                },
                ...
            ]
        }
    }
}
```

## Slicing

An optional parameter `first` can be used to limit the number of items returned in a result list. 

The following query for example, would allow you to return only a single 8.SET Compose product set for a product with the SKU `123456-7890` in your catalogue:

```text
productSets(input: {queryType: SKU, value: "123456-7890"}, first: 1) {
    edges {
        node {
            title
        }
    }
}
```

You can pass an arbitrary positive integer to the `first` argument. Bear in mind though, that the result will always be the same shape, even if you request a single item. So the above query would result in:

```text
{
    "data": {
        "productSets": {
            "edges": [
                {
                    "node" : {
                        "title": "Product Set Example 1"
                    }
                }
            ]
        }
    }
}
```

## Cursor-based pagination

{% hint style="danger" %}
As mentioned above, pagination is not yet fully implemented. The following section is thus just a preview of how to use the cursor-based, forward pagination once it will be implemented.
{% endhint %}

The `after` parameter can be used to traverse through a paginated result. It expects a cursor value which can be obtained from the previous response.

Using a combination of slicing and cursor-based pagination for example, you could iterate through a list of 8.SET Compose product sets one by one:

```text
productSets(
    input: {queryType: SKU, value: "123456-7890"}, 
    first: 1
) {
    edges {
        cursor
        node {
            title
        }
    }
    pageInfo {
        endCursor
    }
}
```

This would result in the following response:

```text
{
    "data": {
        "productSets": {
            "edges": [
                {
                    "node" : {
                        "title": "Product Set Example 1"
                    }
                }
            ],
            "pageInfo": {
                "endCursor": "Zjk3NzA3ZTEtMWNiYS00YWQ0LWFiNDQtM2VmNTM0ZWYzNWUx"
            }
        }
    }
}
```

Now using the cursor from this response we can query the next product set:

```text
productSets(
    input: {queryType: SKU, value: "123456-7890"}, 
    after: "Zjk3NzA3ZTEtMWNiYS00YWQ0LWFiNDQtM2VmNTM0ZWYzNWUx", 
    first: 1
) {
    edges {
        node {
            title
        }
    }
    pageInfo {
        endCursor
    }
}
```

Which would in turn respond with the following result:

```text
{
    "data": {
        "productSets": {
            "edges": [
                {
                    "node" : {
                        "title": "Product Set Example 2"
                    }
                }
            ],
            "pageInfo": {
                "endCursor": "NjIzMjZkM2ItN2M0My00MTNjLWJhMjUtZWNhMDhhOGExMDE0"
            }
        }
    }
}
```

Following this pattern we could continue traversing through the list of **all** relevant product sets. Additionally, this approach is very flexible and even enables changing slice sizes between consecutive queries as the used cursor is always based on the previous result.

