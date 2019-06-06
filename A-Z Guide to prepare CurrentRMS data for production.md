# 1. Add **configuration options custom fields** to the "Product" module

Some products may have different configuration options, such as:
..*color (red, yellow, etc)
      - size (S, M, L, etc)
      - wattage (100 Watt, 200 Watt etc)
Not all products necessarily have them, but to be able to configure them for products that do, we need to set up ```Custom fields``` in CurrentRMS, which will make these configuration options globally available for all products.

1. Add a ```Custom Field Group``` named ```custom_product_config_options```
    - System Setup -> Custom Field Groups -> Add Custom Field Group
    - Name it ```custom_product_config_options```

    ![1.png](https://bitbucket.org/repo/qEd965M/images/2230219713-1.png)

1.2 Add a ```List of Values``` for each possible product configuration option
For each product configuration option there is, add a ```List of Values``` with a name that starts with: ```custom_product_config_option_``` followed by a term that describes what the option is. For example: ```custom_product_config_option_color``` -or- ```custom_product_config_option_size``` -or- ```custom_product_config_option_wattage``` etc etc. Do the following:
    - System Setup -> List of Values -> Add List of Values
    - set name to something that conforms the above mentioned naming convention, such as ```custom_product_config_option_size```
    - add all possible values this option can have with **+ add a new list of values entry**
    - set a default value

    ![2.png](https://bitbucket.org/repo/qEd965M/images/531879093-2.png)

1.3 Add a **custom field** for each possible product configuration option to **Product**
For each product configuration option there is, add a ```custom field``` with a name that starts with: ```custom_product_config_option_``` followed by a term that describes what the option is. For example: ```custom_product_config_option_color``` -or- ```custom_product_config_option_size``` -or- ```custom_product_config_option_wattage``` etc etc. Do the following:
    - System Setup -> Custom Field -> Add Custom Field
    - set name to something that conforms the above mentioned naming convention, such as ```custom_product_config_option_size```
    - choose module ```Product```
    - choose the custom field group ```custom_product_config_options```
    - leave **order** as it is to 0
    - choose field type ```Multi List of Values```
    - choose for **List name** the **List of Values** we just created with the same name for this option

    ![3.png](https://bitbucket.org/repo/qEd965M/images/179181507-3.png)

1.4 Set the possible option values for applicable products
After you have add a **custom field** for each possible product configuration option, every time you add a new product or edit an existing product, the configuration options will be shown. By default none of them will be checked.

    ![4.png](https://bitbucket.org/repo/qEd965M/images/2022924038-4.png)

So For each ```Product``` that has different configurations, check the possible values to that specific custom field that apply to them in the Product Detail panel, for example the following screenshot shows that the product has a **pink** and **yellow** version, and none of the other possible configuration options apply to it:

   ![5.png](https://bitbucket.org/repo/qEd965M/images/1699072459-5.png)

All selected **configuration options and their values** for a product WILL be shown in the rental platform frontend in the **product detail** page. The button ```Advanced Configuration``` becomes visible in the ```Add to cart``` pane:

   ![6.png](https://bitbucket.org/repo/qEd965M/images/3428544830-6.png)

And the and the possible configurations will be selectable for the user:

   ![7.png](https://bitbucket.org/repo/qEd965M/images/3019550241-7.png)

# 2. Add **description custom fields** to the "Product" module