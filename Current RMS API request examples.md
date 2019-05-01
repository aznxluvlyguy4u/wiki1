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