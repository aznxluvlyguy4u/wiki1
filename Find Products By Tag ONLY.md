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