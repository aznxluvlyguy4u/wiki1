Find Products By [Name OR ProductGroup name OR Tag]

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