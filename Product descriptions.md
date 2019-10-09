# Product descriptions

This section describes adding **description custom fields** to the "Product" module.

To be able to fully customize the way product description is rendered in the rental platform **product detail** page, custom fields need to be made and added to the "**Product**" module. In current version of this guide the following layout is used as template, but **__THIS CAN BE CHANGED IN LATER VERSION__**:

![9.png](https://bitbucket.org/repo/qEd965M/images/18129596-9.png)

* 2.1 Add a `Custom Field Group` named `custom_product_description`
    - System Setup -> Custom Field Groups -> Add Custom Field Group
    - Name it `custom_product_description`
    - Leave **Order** to `0`

    ![8.png](https://bitbucket.org/repo/qEd965M/images/352362168-8.png)

* 2.2 Add a list **custom fields** to the **Product** module

The following custom fields must be added individually so that the proposed layout can be rendered:

* `custom_product_description_summary`
* `custom_product_description_seo_title`
* `custom_product_description_head_1`
* `custom_product_description_paragraph_1`
* `custom_product_description_head_2`
* `custom_product_description_paragraph_2`
* `custom_product_description_head_3`
* `custom_product_description_paragraph_3`
* `custom_product_description_head_4`
* `custom_product_description_paragraph_4`
* `custom_product_description_head_5`
* `custom_product_description_paragraph_5`

Do the following for each above mentioned:

- System Setup -> Custom Field -> Add Custom Field
- set corresponding name
- choose module `Product`
- choose the custom field group `custom_product_description`
- set the **order** to `0` for the first item, then add `1` for each following item. (0, 1, 2, 3...)
- choose field type `Text`

![10.png](https://bitbucket.org/repo/qEd965M/images/4195670066-10.png)

After adding all above mentioned description custom fields, they can be filled in during creating new product or editing existing products. When text is filled in these fields, they will be shown in the **description in product detail page**