## Serviceability Requests

**Endpoint Summary**

| Action | Endpoint |
| ------ | -------- |
| List all serviceability requests | `GET /serviceability-requests` |
| Get a serviceability request (includes all serviceability responses) | `GET /serviceability-requests/:id` |
| Create a serviceability request | `POST /serviceability-requests` |
| Update a serviceability request | `PUT /serviceability-requests/:id` |
| Cancel a serviceability request | `POST /serviceability-requests/:id/cancel` |
| Delete a serviceability request | `DELETE /serviceability-requests/:id` |

### List serviceability requests

```
GET /serviceability-requests
```
**Response**

Status: 200 OK
``` JSON
{
  "link": {
    "href": "/api/serviceability-requests"  
  },
  "available": 1,
  "returned": 1,
  "items": [
    {
      "objectType": "serviceabilityRequest",
      "id": "SRQ-YY-13043135",
      "link": {
        "href": "/api/serviceability-requests/SRQ-YY-13043135"
      },
      "buyerId": "Buyer",
      "sellerId": "Seller",
      "status": "SUBMITTED",
      "projectId": "PRJ-YY-12345678",
      "pricingMethod": "CONTRACT",
      "pricingReference": "YY-MES-0192",
      "serviceSite" : {
        "objectType": "serviceSiteInformation",
        "siteAddressType": "FORMATTED_ADDRESS",
        "siteAddress": {
          "addressLine1": "5630 E SANTA ANA CANYON RD",
          "addressLine2": "STE 100",
          "city": "ANAHEIM",
          "stateOrProvince": "CA",
          "country": "USA",
          "postCode": "92807",
          "postCodeExtension": "1234"
        }
      },
      "primarySiteContact": {
        "objectType": "contact",
        "name": "Frederick Fullerton",
        "telephoneNumber": "6574459867",
        "email": "f_fullerton@libertyproperty.com"
      },
      "alternateSiteContact": {
        "objectType": "contact",
        "name": "Betty Buckminster",
        "telephoneNumber": "7147651026",
        "email": "b_buckminster@libertyproperty.com"
      },
      "desiredResponseDate": "2016-09-26T12:00:00.333Z",
      "serviceDetail": {
        "objectType": "ethernetServiceDetail",
        "serviceCategory": "ETHERNET",
        "serviceType": "AYYESS_EPL",
        "bandwidth": {
          "objectType": "informationRateQuantity",
          "amount": 100,
          "quantity": "Mbps"
        },
        "maxPortSpeed": {
          "objectType": "informationRateQuantity",
          "amount": 1,
          "quantity": "Gbps"
        },
        "interfaceType": "OPTICAL",
        "accessMedium": "FIBER",
        "newEnniRequired": false,
        "buyerEnniId": "YY-ENNI-12345678",
        "classOfService": "HIGH",
        "pricingTerm": "24",
        "desiredActivationDate": "2016-10-26T12:00:00.333Z"
      }
    }
  ]
}
```

### Get serviceability request

```
GET /serviceability-requests/:id
```
**Response**

Status: 200 OK
``` JSON
{
  "objectType": "serviceabilityRequest",
  "id": "SRQ-YY-13043135",
  "link": {
    "href": "/api/serviceability-requests/SRQ-YY-13043135"
  },
  "buyerId": "Buyer",
  "sellerId": "Seller",
  "status": "SUBMITTED",
  "projectId": "PRJ-YY-12345678",
  "pricingMethod": "CONTRACT",
  "pricingReference": "YY-MES-0192",
  "serviceSite" : {
    "objectType": "serviceSiteInformation",
    "siteAddressType": "FORMATTED_ADDRESS",
    "siteAddress": {
      "addressLine1": "5630 E SANTA ANA CANYON RD",
      "addressLine2": "STE 100",
      "city": "ANAHEIM",
      "stateOrProvince": "CA",
      "country": "USA",
      "postCode": "92807",
      "postCodeExtension": "1234"
    }
  },
  "primarySiteContact": {
    "objectType": "contact",
    "name": "Frederick Fullerton",
    "telephoneNumber": "6574459867",
    "email": "f_fullerton@libertyproperty.com"
  },
  "alternateSiteContact": {
    "objectType": "contact",
    "name": "Betty Buckminster",
    "telephoneNumber": "7147651026",
    "email": "b_buckminster@libertyproperty.com"
  },
  "desiredResponseDate": "2016-09-26T12:00:00.333Z",
  "serviceDetail": {
    "objectType": "ethernetServiceDetail",
    "serviceCategory": "ETHERNET",
    "serviceType": "AYYESS_EPL",
    "bandwidth": {
      "objectType": "informationRateQuantity",
      "amount": 100,
      "quantity": "Mbps"
    },
    "maxPortSpeed": {
      "objectType": "informationRateQuantity",
      "amount": 1,
      "quantity": "Gbps"
    },
    "interfaceType": "OPTICAL",
    "accessMedium": "FIBER",
    "newEnniRequired": false,
    "buyerEnniId": "YY-ENNI-12345678",
    "classOfService": "HIGH",
    "pricingTerm": "24",
    "desiredActivationDate": "2016-10-26T12:00:00.333Z"
  }
}
```

### Create serviceability request

```
POST /serviceability-requests
```

**Example**

```JSON
{
  "objectType": "serviceabilityRequest-create-update",
  "buyerId": "Buyer",
  "sellerId": "Seller",
  "projectId": "PRJ-YY-12345678",
  "pricingMethod": "CONTRACT",
  "pricingReference": "YY-MES-0192",
  "serviceSite" : {
    "objectType": "serviceSiteInformation",
    "siteAddressType": "FORMATTED_ADDRESS",
    "siteAddress": {
      "addressLine1": "5630 E SANTA ANA CANYON RD",
      "addressLine2": "STE 100",
      "city": "ANAHEIM",
      "stateOrProvince": "CA",
      "country": "USA",
      "postCode": "92807",
      "postCodeExtension": "1234"
    }
  },
  "primarySiteContact": {
    "objectType": "contact",
    "name": "Frederick Fullerton",
    "telephoneNumber": "6574459867",
    "email": "f_fullerton@libertyproperty.com"
  },
  "alternateSiteContact": {
    "objectType": "contact",
    "name": "Betty Buckminster",
    "telephoneNumber": "7147651026",
    "email": "b_buckminster@libertyproperty.com"
  },
  "desiredResponseDate": "2016-09-26T12:00:00.333Z",
  "serviceDetail": {
    "objectType": "ethernetServiceDetail",
    "serviceCategory": "ETHERNET",
    "serviceType": "AYYESS_EPL",
    "bandwidth": {
      "objectType": "informationRateQuantity",
      "amount": 100,
      "quantity": "Mbps"
    },
    "maxPortSpeed": {
      "objectType": "informationRateQuantity",
      "amount": 1,
      "quantity": "Gbps"
    },
    "interfaceType": "OPTICAL",
    "accessMedium": "FIBER",
    "newEnniRequired": false,
    "buyerEnniId": "YY-ENNI-12345678",
    "classOfService": "HIGH",
    "pricingTerm": "24",
    "desiredActivationDate": "2016-10-26T12:00:00.333Z"
  }
}
```

**Response**

Status: 201 Created
```JSON
{
  "objectType": "serviceabilityRequest",
  "id": "SRQ-YY-13043135",
  "link": {
    "href": "/api/serviceability-requests/SRQ-YY-13043135"
  },
  "buyerId": "Buyer",
  "sellerId": "Seller",
  "status": "SUBMITTED",
  "projectId": "PRJ-YY-12345678",
  "pricingMethod": "CONTRACT",
  "pricingReference": "YY-MES-0192",
  "serviceSite" : {
    "objectType": "serviceSiteInformation",
    "siteAddressType": "FORMATTED_ADDRESS",
    "siteAddress": {
      "addressLine1": "5630 E SANTA ANA CANYON RD",
      "addressLine2": "STE 100",
      "city": "ANAHEIM",
      "stateOrProvince": "CA",
      "country": "USA",
      "postCode": "92807",
      "postCodeExtension": "1234"
    }
  },
  "primarySiteContact": {
    "objectType": "contact",
    "name": "Frederick Fullerton",
    "telephoneNumber": "6574459867",
    "email": "f_fullerton@libertyproperty.com"
  },
  "alternateSiteContact": {
    "objectType": "contact",
    "name": "Betty Buckminster",
    "telephoneNumber": "7147651026",
    "email": "b_buckminster@libertyproperty.com"
  },
  "desiredResponseDate": "2016-09-26T12:00:00.333Z",
  "serviceDetail": {
    "objectType": "ethernetServiceDetail",
    "serviceCategory": "ETHERNET",
    "serviceType": "AYYESS_EPL",
    "bandwidth": {
      "objectType": "informationRateQuantity",
      "amount": 100,
      "quantity": "Mbps"
    },
    "maxPortSpeed": {
      "objectType": "informationRateQuantity",
      "amount": 1,
      "quantity": "Gbps"
    },
    "interfaceType": "OPTICAL",
    "accessMedium": "FIBER",
    "newEnniRequired": false,
    "buyerEnniId": "YY-ENNI-12345678",
    "classOfService": "HIGH",
    "pricingTerm": "24",
    "desiredActivationDate": "2016-10-26T12:00:00.333Z"
  }
}
```

### Update serviceability request

```
PUT /serviceability-requests/SRQ-YY-13043135
```

**Example**

```JSON
{
  "objectType": "serviceabilityRequest-create-update",
  "buyerId": "Buyer",
  "sellerId": "Seller",
  "projectId": "PRJ-YY-12345678",
  "pricingMethod": "CONTRACT",
  "pricingReference": "YY-MES-0192",
  "serviceSite" : {
    "objectType": "serviceSiteInformation",
    "siteAddressType": "FORMATTED_ADDRESS",
    "siteAddress": {
      "addressLine1": "5630 E SANTA ANA CANYON RD",
      "addressLine2": "STE 100",
      "city": "ANAHEIM",
      "stateOrProvince": "CA",
      "country": "USA",
      "postCode": "92807",
      "postCodeExtension": "1234"
    }
  },
  "primarySiteContact": {
    "objectType": "contact",
    "name": "Frederick Fullerton",
    "telephoneNumber": "6574459867",
    "email": "f_fullerton@libertyproperty.com"
  },
  "alternateSiteContact": {
    "objectType": "contact",
    "name": "Betty Buckminster",
    "telephoneNumber": "7147651026",
    "email": "b_buckminster@libertyproperty.com"
  },
  "desiredResponseDate": "2016-09-26T12:00:00.333Z",
  "serviceDetail": {
    "objectType": "ethernetServiceDetail",
    "serviceCategory": "ETHERNET",
    "serviceType": "AYYESS_EPL",
    "bandwidth": {
      "objectType": "informationRateQuantity",
      "amount": 100,
      "quantity": "Mbps"
    },
    "maxPortSpeed": {
      "objectType": "informationRateQuantity",
      "amount": 1,
      "quantity": "Gbps"
    },
    "interfaceType": "OPTICAL",
    "accessMedium": "FIBER",
    "newEnniRequired": false,
    "buyerEnniId": "YY-ENNI-12345678",
    "classOfService": "HIGH",
    "pricingTerm": "24",
    "desiredActivationDate": "2016-10-26T12:00:00.333Z"
  }
}
```

**Response**

Status: 200 OK
```JSON
{
  "objectType": "serviceabilityRequest",
  "id": "SRQ-YY-13043135",
  "link": {
    "href": "/api/serviceability-requests/SRQ-YY-13043135"
  },
  "buyerId": "Buyer",
  "sellerId": "Seller",
  "status": "SUBMITTED",
  "projectId": "PRJ-YY-12345678",
  "pricingMethod": "CONTRACT",
  "pricingReference": "YY-MES-0192",
  "serviceSite" : {
    "objectType": "serviceSiteInformation",
    "siteAddressType": "FORMATTED_ADDRESS",
    "siteAddress": {
      "addressLine1": "5630 E SANTA ANA CANYON RD",
      "addressLine2": "STE 100",
      "city": "ANAHEIM",
      "stateOrProvince": "CA",
      "country": "USA",
      "postCode": "92807",
      "postCodeExtension": "1234"
    }
  },
  "primarySiteContact": {
    "objectType": "contact",
    "name": "Frederick Fullerton",
    "telephoneNumber": "6574459867",
    "email": "f_fullerton@libertyproperty.com"
  },
  "alternateSiteContact": {
    "objectType": "contact",
    "name": "Betty Buckminster",
    "telephoneNumber": "7147651026",
    "email": "b_buckminster@libertyproperty.com"
  },
  "desiredResponseDate": "2016-09-26T12:00:00.333Z",
  "serviceDetail": {
    "objectType": "ethernetServiceDetail",
    "serviceCategory": "ETHERNET",
    "serviceType": "AYYESS_EPL",
    "bandwidth": {
      "objectType": "informationRateQuantity",
      "amount": 100,
      "quantity": "Mbps"
    },
    "maxPortSpeed": {
      "objectType": "informationRateQuantity",
      "amount": 1,
      "quantity": "Gbps"
    },
    "interfaceType": "OPTICAL",
    "accessMedium": "FIBER",
    "newEnniRequired": false,
    "buyerEnniId": "YY-ENNI-12345678",
    "classOfService": "HIGH",
    "pricingTerm": "24",
    "desiredActivationDate": "2016-10-26T12:00:00.333Z"
  }
}
```

### Cancel serviceability request

```
POST /serviceability-requests/SRQ-YY-13043135/cancel
```

**Response**

Status: 200 OK

### Delete serviceability request

```
DELETE /serviceability-requests/SRQ-YY-13043135/
```

**Response**

Status: 200 OK
