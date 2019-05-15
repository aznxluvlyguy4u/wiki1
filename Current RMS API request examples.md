#Find Products By [Name OR ProductGroup name OR Tag]

```
GET https://api.current-rms.com/api/v1/products?page=1&per_page=2&q[name_or_product_group_name_or_product_tags_name_cont]=seabob

page (number, optional)	1	
The requested page number

per_page (number, optional)	20	
The number of records to return for the requested page

filtermode (string, optional)	all	
A built in filtermode name (e.g. active, inactive, all)

q[name_or_product_group_name_or_tags_name_cont] (string, optional)	search_text_here	
Search on name, product group name or tags for matching records

```
```json
{
    "products": [
        {
            "id": 17,
            "name": "Bag for Seabob F5 series",
            "type": "Product",
            "tag_list": [
                "Seabob Bag"
            ],
            "description": "Seabob bag",
            "allowed_stock_type": 0,
            "allowed_stock_type_name": "All",
            "stock_method": 1,
            "stock_method_name": "Bulk",
            "buffer_percent": "0.0",
            "post_rent_unavailability": 0,
            "replacement_charge": "285.0",
            "weight": "4.0",
            "barcode": "SBAGF5",
            "active": true,
            "accessory_only": true,
            "system": false,
            "discountable": true,
            "rental_rate": {
                "item_id": 17,
                "store_id": 1,
                "transaction_type": 1,
                "rate_definition_id": 3,
                "price": "10.0",
                "deposit": "0.0",
                "category_prices": [],
                "properties": {
                    "day_price": "0.0",
                    "hour_price": "0.0",
                    "__value_types": "---\nday_price: BigDecimal\nhour_price: BigDecimal\ndistance_price: BigDecimal\nflat_rate_price: BigDecimal\n",
                    "distance_price": "0.0",
                    "flat_rate_price": "0.0"
                },
                "priority": 0,
                "date_range": "1900-01-01...3000-01-01"
            },
            "sale_rate": null,
            "product_group_id": 24,
            "tax_class_id": 2,
            "rental_revenue_group_id": 1,
            "sale_revenue_group_id": 6,
            "sub_rental_cost_group_id": 3,
            "purchase_cost_group_id": 3,
            "created_at": "2019-04-30T13:47:36.600Z",
            "updated_at": "2019-04-30T13:47:36.749Z",
            "custom_fields": {
                "public_icon_url": "",
                "public_icon_thumb_url": ""
            },
            "product_group": {
                "id": 24,
                "name": "Seabob",
                "description": "All Seabob Models + Accessories",
                "created_at": "2019-04-30T12:46:53.303Z",
                "updated_at": "2019-04-30T12:46:53.303Z",
                "custom_fields": {}
            },
            "tax_class": {
                "id": 2,
                "name": "Default"
            },
            "icon": {
                "id": 16,
                "iconable_id": 17,
                "iconable_type": "Item",
                "image_file_name": "bag.jpg",
                "url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/16/original/bag.jpg",
                "thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/16/thumb/bag.jpg",
                "created_at": "2019-04-30T13:47:36.612Z",
                "updated_at": "2019-04-30T13:47:36.612Z"
            },
            "rental_revenue_group": {
                "id": 1,
                "name": "Rental",
                "description": "",
                "active": true
            },
            "sale_revenue_group": {
                "id": 6,
                "name": "Sale of goods",
                "description": "",
                "active": true
            },
            "sub_rental_cost_group": {
                "id": 3,
                "name": "Other",
                "description": "",
                "active": true
            },
            "purchase_cost_group": {
                "id": 3,
                "name": "Other",
                "description": "",
                "active": true
            },
            "accessories": [],
            "alternative_products": [],
            "attachments": [],
            "rental_rates": [
                {
                    "id": 68,
                    "store_id": null,
                    "store_name": "",
                    "transaction_type": 1,
                    "transaction_type_name": "Rental",
                    "rate_definition_id": 3,
                    "rate_definition_name": "Daily Rate",
                    "starts_at": null,
                    "ends_at": null,
                    "price": "10.0",
                    "category_prices": []
                }
            ],
            "sale_rates": []
        },
    ...
```

# Find Products By Tag ONLY
```
GET https://api.current-rms.com/api/v1/products?tags=["sierra"]
```
```json
{
    "products": [
        {
            "id": 163,
            "name": "Sierra",
            "type": "Product",
            "tag_list": [
                "Sierra"
            ],
            "description": "Aquaglide Sierra item for Obstacle course or Aquapark",
            "allowed_stock_type": 0,
            "allowed_stock_type_name": "All",
            "stock_method": 2,
            "stock_method_name": "Serialised",
            "buffer_percent": "0.0",
            "post_rent_unavailability": 0,
            "replacement_charge": "2268.0",
            "weight": "39.0",
            "barcode": "",
            "active": true,
            "accessory_only": false,
            "system": false,
            "discountable": true,
            "rental_rate": {
                "item_id": 163,
                "store_id": 1,
                "transaction_type": 1,
                "rate_definition_id": 3,
                "price": "70.0",
                "deposit": "0.0",
                "category_prices": [],
                "properties": {
                    "day_price": "0.0",
                    "hour_price": "0.0",
                    "__value_types": "---\nday_price: BigDecimal\nhour_price: BigDecimal\ndistance_price: BigDecimal\nflat_rate_price: BigDecimal\n",
                    "distance_price": "0.0",
                    "flat_rate_price": "0.0"
                },
                "priority": 0,
                "date_range": "1900-01-01...3000-01-01"
            },
            "sale_rate": {
                "item_id": 163,
                "store_id": 1,
                "transaction_type": 2,
                "rate_definition_id": null,
                "price": "0.0",
                "deposit": "0.0",
                "category_prices": [],
                "properties": {
                    "day_price": "0.0",
                    "hour_price": "0.0",
                    "__value_types": "---\nday_price: BigDecimal\nhour_price: BigDecimal\ndistance_price: BigDecimal\nflat_rate_price: BigDecimal\n",
                    "distance_price": "0.0",
                    "flat_rate_price": "0.0"
                },
                "priority": 0,
                "date_range": "1900-01-01...3000-01-01"
            },
            "product_group_id": 16,
            "tax_class_id": 2,
            "rental_revenue_group_id": 1,
            "sale_revenue_group_id": 6,
            "sub_rental_cost_group_id": 3,
            "purchase_cost_group_id": 3,
            "created_at": "2019-04-30T13:48:49.554Z",
            "updated_at": "2019-04-30T13:48:49.704Z",
            "custom_fields": {
                "public_icon_url": "",
                "public_icon_thumb_url": ""
            },
            "product_group": {
                "id": 16,
                "name": "Aqua Park",
                "description": "Pools, Climbing Wall, docks, Blob, Bouncers, Zorbs, Floating Slides, Mountains, Runways, Swimsteps, Junglojoes, Rockits, etc + accessories",
                "created_at": "2019-04-30T12:46:53.268Z",
                "updated_at": "2019-04-30T12:46:53.268Z",
                "custom_fields": {}
            },
            "tax_class": {
                "id": 2,
                "name": "Default"
            },
            "icon": {
                "id": 161,
                "iconable_id": 163,
                "iconable_type": "Item",
                "image_file_name": "AGLSI.jpg.png",
                "url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/161/original/AGLSI.jpg.png",
                "thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/161/thumb/AGLSI.jpg.png",
                "created_at": "2019-04-30T13:48:49.572Z",
                "updated_at": "2019-04-30T13:48:49.572Z"
            },
            "rental_revenue_group": {
                "id": 1,
                "name": "Rental",
                "description": "",
                "active": true
            },
            "sale_revenue_group": {
                "id": 6,
                "name": "Sale of goods",
                "description": "",
                "active": true
            },
            "sub_rental_cost_group": {
                "id": 3,
                "name": "Other",
                "description": "",
                "active": true
            },
            "purchase_cost_group": {
                "id": 3,
                "name": "Other",
                "description": "",
                "active": true
            },
            "accessories": [
                {
                    "id": 261,
                    "relatable_id": 163,
                    "relatable_type": "Item",
                    "related_id": 126,
                    "related_type": "Item",
                    "related_name": "Pump 220V",
                    "related_icon_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/124/original/09-T110v-LG.jpg",
                    "related_icon_thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/124/thumb/09-T110v-LG.jpg",
                    "type": "Accessory",
                    "parent_transaction_type": 0,
                    "parent_transaction_type_name": "rent or sell",
                    "item_transaction_type": 1,
                    "item_transaction_type_name": "rented",
                    "inclusion_type": 0,
                    "inclusion_type_name": "default",
                    "mode": 0,
                    "mode_name": "accessory",
                    "quantity": "1.0",
                    "zero_priced": true,
                    "sort_order": 0,
                    "created_at": "2019-04-30T13:50:39.175Z",
                    "updated_at": "2019-04-30T13:50:39.175Z"
                },
                {
                    "id": 262,
                    "relatable_id": 163,
                    "relatable_type": "Item",
                    "related_id": 11,
                    "related_type": "Item",
                    "related_name": "Aquaglide Repair Kit",
                    "related_icon_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/10/original/Hobie-New-I-series-inflatable-kayak-repair-kit.jpg",
                    "related_icon_thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/10/thumb/Hobie-New-I-series-inflatable-kayak-repair-kit.jpg",
                    "type": "Accessory",
                    "parent_transaction_type": 0,
                    "parent_transaction_type_name": "rent or sell",
                    "item_transaction_type": 1,
                    "item_transaction_type_name": "rented",
                    "inclusion_type": 0,
                    "inclusion_type_name": "default",
                    "mode": 0,
                    "mode_name": "accessory",
                    "quantity": "1.0",
                    "zero_priced": true,
                    "sort_order": 1,
                    "created_at": "2019-04-30T13:50:39.186Z",
                    "updated_at": "2019-04-30T13:50:39.186Z"
                },
                {
                    "id": 263,
                    "relatable_id": 163,
                    "relatable_type": "Item",
                    "related_id": 85,
                    "related_type": "Item",
                    "related_name": "Interlock System",
                    "related_icon_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/83/original/09_InterlocSet_14729_1409094949_195_234__78723.1427841950.200.200.jpg",
                    "related_icon_thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/83/thumb/09_InterlocSet_14729_1409094949_195_234__78723.1427841950.200.200.jpg",
                    "type": "Accessory",
                    "parent_transaction_type": 0,
                    "parent_transaction_type_name": "rent or sell",
                    "item_transaction_type": 1,
                    "item_transaction_type_name": "rented",
                    "inclusion_type": 2,
                    "inclusion_type_name": "optional",
                    "mode": 0,
                    "mode_name": "accessory",
                    "quantity": "0.0",
                    "zero_priced": false,
                    "sort_order": 2,
                    "created_at": "2019-04-30T13:50:39.197Z",
                    "updated_at": "2019-04-30T13:50:39.197Z"
                },
                {
                    "id": 264,
                    "relatable_id": 163,
                    "relatable_type": "Item",
                    "related_id": 70,
                    "related_type": "Item",
                    "related_name": "Heavy duty Carry Bag for Inflatables",
                    "related_icon_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/68/original/inflatables-protective-bag.jpg",
                    "related_icon_thumb_url": "https://s3.amazonaws.com/current-rms/03f6d620-26db-0137-df25-12fbcfdb731a/icons/68/thumb/inflatables-protective-bag.jpg",
                    "type": "Accessory",
                    "parent_transaction_type": 0,
                    "parent_transaction_type_name": "rent or sell",
                    "item_transaction_type": 1,
                    "item_transaction_type_name": "rented",
                    "inclusion_type": 0,
                    "inclusion_type_name": "default",
                    "mode": 0,
                    "mode_name": "accessory",
                    "quantity": "1.0",
                    "zero_priced": true,
                    "sort_order": 3,
                    "created_at": "2019-04-30T13:50:39.205Z",
                    "updated_at": "2019-04-30T13:50:39.205Z"
                }
            ],
            "alternative_products": [],
            "attachments": [],
            "rental_rates": [
                {
                    "id": 628,
                    "store_id": null,
                    "store_name": "",
                    "transaction_type": 1,
                    "transaction_type_name": "Rental",
                    "rate_definition_id": 3,
                    "rate_definition_name": "Daily Rate",
                    "starts_at": null,
                    "ends_at": null,
                    "price": "70.0",
                    "category_prices": []
                }
            ],
            "sale_rates": [
                {
                    "id": 630,
                    "store_id": null,
                    "store_name": "",
                    "transaction_type": 2,
                    "transaction_type_name": "Sale",
                    "rate_definition_id": null,
                    "rate_definition_name": null,
                    "starts_at": null,
                    "ends_at": null,
                    "price": "0.0",
                    "category_prices": []
                }
            ]
        }
    ],
    "meta": {
        "total_row_count": 1,
        "row_count": 1,
        "page": 1,
        "per_page": 20
    }
}
```

# Find Products by Product Group ONLY (2 options same result)
```
1. By name
GET https://api.current-rms.com/api/v1/products?q[product_group_name_cont]=Fun_Activities
```
```
2. By product group id
GET https://api.current-rms.com/api/v1/products?q[product_group_id_eq]=19
```

# Find Product by Product ID
```
GET https://api.current-rms.com/api/v1/products/19
```

# Find All Product Groups
```
GET https://api.current-rms.com/api/v1/product_groups
```

# Find Products based on mixed query params
```
GET https://oceanpremium-staging.current-rms.com/products?product_group_id_eq=22&tags=["Fins"]
```

# Get availability of a single product
```
POST https://api.current-rms.com/api/v1/availability/product
```
## of one single store
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

# Find Products inventory / availability By [Name OR ProductGroup name OR Tag] AND date range AND STORE ID
```
https://api.current-rms.com/api/v1/products/inventory?starts_at=2019-05-10%2000:00:00.000000&ends_at=2019-05-15%2023:59:59.999999&filtermode[]=rental&store_id=5&q[name_or_product_group_name_or_product_tags_name_cont]=flyboard
```

returns
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