# 1. Add "Custom Field" "product_options" to the "Product" module

Some products may have different configuration options, such as:
    - color (red, yellow, etc)
    - size (S, M, L, etc)
    - wattage (100 Watt, 200 Watt etc)

Not all products necessarily have them, but to be able to configure them for products that do, we need to set up ```Custom fields``` in CurrentRMS, which will make these configuration options globally available for all products.

1. Add a ```Custom Field Group``` named ```custom_product_config_options```
    - System Setup -> Custom Field Groups -> Add Custom Field Group ```custom_product_config_options```
    ![1.png](https://bitbucket.org/repo/qEd965M/images/2230219713-1.png)

2. Add a ```List of Value``` named ```Product Option```
    - System Setup -> List of Values -> Add List of Values ```Product Option```
    - Add the options that any product can have, and prefix it with ```product_option_``` such as ```product_option_size```
    ![1-add-product-option-list-of-values.png](https://bitbucket.org/repo/qEd965M/images/1707896004-1-add-product-option-list-of-values.png)



3. Add a ```Custom Field``` named ```product_options```
    - System Setup -> Custom Field -> Add Custom Field ```product_options```
    - choose custom field group ```Product Options```
    - choose module ```Product```
    - choose field type ```Multi List of Values```
    - choose list name ```Product Option```
    ![3-add-product-options-custom-field.png](https://bitbucket.org/repo/qEd965M/images/1684220058-3-add-product-options-custom-field.png)

4. For each existing ```Product``` or to be created product, set the custom field ```product_options``` with values that THAT specific product can have in the Product Detail panel
    - For example the product **Seabob F5 S** can have the following options:
    ![4-set-product-product-options.png](https://bitbucket.org/repo/qEd965M/images/2177113834-4-set-product-product-options.png)