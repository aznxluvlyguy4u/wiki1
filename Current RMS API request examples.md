# Current RMS API request examples

## Table of Content

|                                                                              |
|------------------------------------------------------------------------------|
| 0. [/api/v1/products/inventory](#markdown-header-products-inventory)         |


## Products inventory 

### Default API behaviour

The _products inventory_ endpoint has some noticeable behaviour that needs to be taken into account
when requests are done.

- If query **does** contain storeID,  but **no** date range, result will revert to availability **on date now**.

- If query does **not** contain storeID, then availability **cannot be inferred**, and the result is just a 'plain' product details payload **and the availability count will always be zero**.

### Configuration instructions within CurrentRMS

Tell Janez to mark ‘Accessory Only’ products ‘Accessory Only’, so that a filtering can be made for products/inventory endpoint.

Then add the condition query param which exclude all ‘Accessory Only’ results

`q[product_accessory_only_eq]=false`

Another option is to add the condition query param which exclude all resulted products that belong to the product group Accessories:

`q[product_product_group_name_not_eq]=Accessories`

OR

`q[product_product_group_id_not_eq]=15`


### Find Products By [Name OR ProductGroup name OR Tag]

`GET https://api.current-rms.com/api/v1/products?page=1&per_page=2&q[name_or_product_group_name_or_product_tags_name_cont]=seabob`

- The requested page number (number, optional: `page=4`	
  
- The number of records to return for the requested page (number, optional): `per_page=20`
  
- A built in filtermode name (e.g. active, inactive, all) - (string, optional): `filtermode[]=all`
 
- Search on name, product group name or tags for matching records (string, optional): `q[name_or_product_group_name_or_tags_name_cont]=THE-SEACH-KEYWORD`

#### Find Products By [Name OR ProductGroup name OR Tag]

[Find Products By [Name OR ProductGroup name OR Tag]](Find%20Products%20By%20%5BName%20OR%20ProductGroup%20name%20OR%20Tag%5D)

###  Find Products By Tag ONLY

```
GET https://api.current-rms.com/api/v1/products?tags=["sierra"]
```

[Find Products By Tag ONLY](Find%20Products%20By%20Tag%20ONLY)

# Find Products by Product Group ONLY (2 options same result)

- By name

`GET https://api.current-rms.com/api/v1/products?q[product_group_name_cont]=Fun_Activities`

- By product group id

`GET https://api.current-rms.com/api/v1/products?q[product_group_id_eq]=19`

# Find Product by Product ID

`GET https://api.current-rms.com/api/v1/products/19`

# Find All Product Groups

`GET https://api.current-rms.com/api/v1/product_groups`

# Find Products based on mixed query params

`GET https://oceanpremium-staging.current-rms.com/products?product_group_id_eq=22&tags=["Fins"]`

# Get availability of a single product
```
POST https://api.current-rms.com/api/v1/availability/product
```

#### Find Products by one single store

POST with in the POST body:

```json
{
  "booking_availability_view_options": {
    "product_id": 50,
    "store_ids": [
      5
    ],
    "starts_at": "2019-05-01",
    "days_period": 28
  }
}
```

results:

```json
{
    "product_bookings": {
        "product_id": 50,
        "product_name": "Flyboard Board with Shoes",
        "stock_method": 2,
        "buffer_percent": "0.0",
        "availability_period": 0,
        "start_date": "2019-05-03",
        "end_date": "2019-05-30",
        "store_quantity_held": {
            "5": [
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0"
            ]
        },
        "quantity_held": [
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0"
        ],
        "quantity_booked": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "quantity_unavailable": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "quantity_available": [
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0",
            "1.0"
        ],
        "quantity_sub_rent": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "quantity_quoted": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "quantity_post_rent": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "product_bookings": []
    }
}
```

## of multiple stores
POST with in the POST body:

```json
{
  "booking_availability_view_options": {
    "product_id": 50,
    "store_ids": [
      5,11
    ],
    "starts_at": "2019-05-01",
    "days_period": 28
  }
}
```

results:

```json
{
    "product_bookings": {
        "product_id": 50,
        "product_name": "Flyboard Board with Shoes",
        "stock_method": 2,
        "buffer_percent": "0.0",
        "availability_period": 0,
        "start_date": "2019-05-01",
        "end_date": "2019-05-28",
        "store_quantity_held": {
            "5": [
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0",
                "1.0"
            ],
            "11": [
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0",
                "2.0"
            ]
        },
        "quantity_held": [
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0"
        ],
        "quantity_booked": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "quantity_unavailable": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "quantity_available": [
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0",
            "3.0"
        ],
        "quantity_sub_rent": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "quantity_quoted": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "quantity_post_rent": [
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0",
            "0.0"
        ],
        "product_bookings": []
    }
}
```

###  Find Products inventory / availability By [Name OR ProductGroup name OR Tag] AND date range AND STORE ID

```
https://api.current-rms.com/api/v1/products/inventory?starts_at=2019-05-10%2000:00:00.000000&ends_at=2019-05-15%2023:59:59.999999&filtermode[]=rental&store_id=5&q[name_or_product_group_name_or_product_tags_name_cont]=flyboard
```

returns:

```json
{
    "products": [
        {
            "id": 47,
            "name": "Flyboard Adapter for BRP - 3 screws",
            "description": "Flyboard Adapter for SeaDoo jetski with 3 screws",
            "icon_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/45/original/flyboard-seadoo-3-bolts-adapter.jpg",
            "icon_thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/45/thumb/flyboard-seadoo-3-bolts-adapter.jpg",
            "product_group_name": "Flying",
            "product_group_id": 18,
            "rental_allowed?": true,
            "can_rent?": false,
            "has_stock?": true,
            "rental_quantity_held": null,
            "rental_quantity_unavailable": null,
            "rental_quantity_booked": null,
            "rental_quantity_sub_rent": null,
            "rental_quantity_available": "2.0",
            "rental_rate_exists?": true,
            "rental_price": "10.0",
            "rental_lead_charge_period_name": "Daily",
            "sale_allowed?": true,
            "can_sell?": false,
            "sale_quantity_held": "0.0",
            "sale_quantity_unavailable": "0.0",
            "sale_quantity_allocated": "0.0",
            "sale_quantity_available": "0.0",
            "sale_price": "0.0",
            "stock_method": 1,
            "stock_method_name": "Bulk",
            "buffer_percent": "0.0",
            "replacement_charge": "145.0",
            "weight": "0.0",
            "barcode": "FLY-BRP-AD3S",
            "active": true,
            "accessory_only": true,
            "discountable": true,
            "tax_class_id": 2,
            "rental_revenue_group_id": 1,
            "sale_revenue_group_id": 6,
            "sub_rental_cost_group_id": 3,
            "purchase_cost_group_id": 3,
            "created_at": "2019-04-30T13:47:48.862Z",
            "updated_at": "2019-04-30T13:47:48.943Z",
            "custom_fields": {
                "store_id": "",
                "public_icon_url": "",
                "public_icon_thumb_url": ""
            }
        },
        {
            "id": 48,
            "name": "Flyboard Adapter for BRP - 4 screws",
            "description": "Flyboard Adapter for SeaDoo jetski with 4 screws",
            "icon_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/46/original/seadoo-seadoo-4-bolts-adapter.jpg",
            "icon_thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/46/thumb/seadoo-seadoo-4-bolts-adapter.jpg",
            "product_group_name": "Flying",
            "product_group_id": 18,
            "rental_allowed?": true,
            "can_rent?": false,
            "has_stock?": true,
            "rental_quantity_held": null,
            "rental_quantity_unavailable": null,
            "rental_quantity_booked": null,
            "rental_quantity_sub_rent": null,
            "rental_quantity_available": "1.0",
            "rental_rate_exists?": true,
            "rental_price": "10.0",
            "rental_lead_charge_period_name": "Daily",
            "sale_allowed?": true,
            "can_sell?": false,
            "sale_quantity_held": "0.0",
            "sale_quantity_unavailable": "0.0",
            "sale_quantity_allocated": "0.0",
            "sale_quantity_available": "0.0",
            "sale_price": "0.0",
            "stock_method": 1,
            "stock_method_name": "Bulk",
            "buffer_percent": "0.0",
            "replacement_charge": "145.0",
            "weight": "0.0",
            "barcode": "FLY-BRP-AD4S",
            "active": true,
            "accessory_only": true,
            "discountable": true,
            "tax_class_id": 2,
            "rental_revenue_group_id": 1,
            "sale_revenue_group_id": 6,
            "sub_rental_cost_group_id": 3,
            "purchase_cost_group_id": 3,
            "created_at": "2019-04-30T13:47:49.349Z",
            "updated_at": "2019-04-30T13:47:49.446Z",
            "custom_fields": {
                "store_id": "",
                "public_icon_url": "",
                "public_icon_thumb_url": ""
            }
        }
    ],
    "meta": {
        "total_row_count": 12,
        "row_count": 2,
        "page": 1,
        "per_page": 2
    }
}
```

# Find Products inventory / availability By [Tag ONLY] AND date range AND STORE ID
```
https://api.current-rms.com/api/v1/products/inventory?starts_at=2019-05-10%2000:00:00.000000&ends_at=2019-05-15%2023:59:59.999999&filtermode[]=rental&store_id=5&q[product_tags_name_cont]=tiwal%20sail
```

returns
```json
{
    "products": [
        {
            "id": 196,
            "name": "Tiwal Sail 5m2",
            "description": "5m2 sail for Tiwal",
            "icon_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/194/original/tiwal-sail.jpg",
            "icon_thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/194/thumb/tiwal-sail.jpg",
            "product_group_name": "Watersports",
            "product_group_id": 26,
            "rental_allowed?": true,
            "can_rent?": true,
            "has_stock?": true,
            "rental_quantity_held": null,
            "rental_quantity_unavailable": null,
            "rental_quantity_booked": null,
            "rental_quantity_sub_rent": null,
            "rental_quantity_available": "2.0",
            "rental_rate_exists?": true,
            "rental_price": "0.0",
            "rental_lead_charge_period_name": "Daily",
            "sale_allowed?": true,
            "can_sell?": true,
            "sale_quantity_held": "0.0",
            "sale_quantity_unavailable": "0.0",
            "sale_quantity_allocated": "0.0",
            "sale_quantity_available": "0.0",
            "sale_price": "0.0",
            "stock_method": 2,
            "stock_method_name": "Serialised",
            "buffer_percent": "0.0",
            "replacement_charge": "0.0",
            "weight": "0.0",
            "barcode": "",
            "active": true,
            "accessory_only": false,
            "discountable": true,
            "tax_class_id": 2,
            "rental_revenue_group_id": 1,
            "sale_revenue_group_id": 6,
            "sub_rental_cost_group_id": 3,
            "purchase_cost_group_id": 3,
            "created_at": "2019-04-30T13:49:03.925Z",
            "updated_at": "2019-04-30T13:49:04.112Z",
            "custom_fields": {
                "size": null,
                "store_id": "",
                "public_icon_url": "",
                "public_icon_thumb_url": ""
            }
        },
        {
            "id": 197,
            "name": "Tiwal Sail 7m2",
            "description": "7m2 sail for Tiwal",
            "icon_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/195/original/tiwal-sail.jpg",
            "icon_thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/195/thumb/tiwal-sail.jpg",
            "product_group_name": "Watersports",
            "product_group_id": 26,
            "rental_allowed?": true,
            "can_rent?": true,
            "has_stock?": true,
            "rental_quantity_held": null,
            "rental_quantity_unavailable": null,
            "rental_quantity_booked": null,
            "rental_quantity_sub_rent": null,
            "rental_quantity_available": "2.0",
            "rental_rate_exists?": true,
            "rental_price": "0.0",
            "rental_lead_charge_period_name": "Daily",
            "sale_allowed?": true,
            "can_sell?": true,
            "sale_quantity_held": "0.0",
            "sale_quantity_unavailable": "0.0",
            "sale_quantity_allocated": "0.0",
            "sale_quantity_available": "0.0",
            "sale_price": "0.0",
            "stock_method": 2,
            "stock_method_name": "Serialised",
            "buffer_percent": "0.0",
            "replacement_charge": "0.0",
            "weight": "0.0",
            "barcode": "",
            "active": true,
            "accessory_only": false,
            "discountable": true,
            "tax_class_id": 2,
            "rental_revenue_group_id": 1,
            "sale_revenue_group_id": 6,
            "sub_rental_cost_group_id": 3,
            "purchase_cost_group_id": 3,
            "created_at": "2019-04-30T13:49:04.446Z",
            "updated_at": "2019-04-30T13:49:04.530Z",
            "custom_fields": {
                "size": null,
                "store_id": "",
                "public_icon_url": "",
                "public_icon_thumb_url": ""
            }
        }
    ],
    "meta": {
        "total_row_count": 2,
        "row_count": 2,
        "page": 1,
        "per_page": 20
    }
}
```