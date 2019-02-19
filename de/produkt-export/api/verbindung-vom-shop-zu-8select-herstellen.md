# Verbindung vom Shop zu 8select herstellen

Ein Shop muss sich bei der 8select CSE registrieren damit die Produktdaten regelmässig abgefragt werden.

## **Request**

**`PUT https://sc.8select.io/shops`**

### **Header**

```javascript
{
    "8select-com-fid": "<feed-id>",
    "8select-com-tid": "<tenant-id>"    
}
```

### **Body**

```javascript
{
  "tenant": {
    "feedId": "<feed-id>",
    "id": "<tenant-id>",
  },
  "shop": {
    "url": "https://www.all4golf.de",
    "software": "Shopware",
    "version": "5.5.3"
  },
  "plugin": {
    "version": "2.0.2",
    "config": {
        "setting": "value"
    }
  },        
  "api": {
    "products": "https://www.all4golf.de/cse-api/products"
  }
}
```

### **Response**

`HTTP 200 OK`

```javascript
{
  "tenant": {
    "feedId": "<feed-id>",
    "id": "<tenant-id>",
  },
  "shop": {
    "url": "https://www.all4golf.de",
    "software": "Shopware",
    "version": "5.5.3"
  },
  "plugin": {
    "version": "2.0.2",
    "config": {
        "setting": "value"
    }
  },        
  "api": {
    "products": "https://www.all4golf.de/cse-api/products"
  }
}
```

