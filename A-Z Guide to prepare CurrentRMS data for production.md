# 1. Add ```configuration options custom fields``` to the "Product" module

Some products may have different configuration options, such as:
      - color (red, yellow, etc)
      - size (S, M, L, etc)
      - wattage (100 Watt, 200 Watt etc)

Not all products necessarily have them, but to be able to configure them for products that do, we need to set up ```Custom fields``` in CurrentRMS, which will make these configuration options globally available for all products.

1. Add a ```Custom Field Group``` named ```custom_product_config_options```
    - System Setup -> Custom Field Groups -> Add Custom Field Group ```custom_product_config_options```
    ![1.png](https://bitbucket.org/repo/qEd965M/images/2230219713-1.png)

2. Add a custom field for each possible product configuration option
For each product configuration option there is, add a ```custom field``` with a name that starts with: **custom_product_config_option_** followed by a term that describes what the option is. For example: ```*custom_product_config_option_color*``` -or- ```*custom_product_config_option_size*``` -or- ```*custom_product_config_option_wattage*``` etc etc. Do the following:

    - System Setup -> Custom Field -> Add Custom Field
    - set name to something that conforms the above mentioned naming convention, such as ```*custom_product_config_option_wattage*```
    - choose the custom field group ```custom_product_config_options```
    - choose module ```Product```
    - choose field type ```Multi List of Values```
    - choose list name ```Product Option```
    ![3-add-product-options-custom-field.png](https://bitbucket.org/repo/qEd965M/images/1684220058-3-add-product-options-custom-field.png)

4. For each existing ```Product``` or to be created product, set the custom field ```product_options``` with values that THAT specific product can have in the Product Detail panel
    - For example the product **Seabob F5 S** can have the following options:
    ![4-set-product-product-options.png](https://bitbucket.org/repo/qEd965M/images/2177113834-4-set-product-product-options.png)