# A to Z guide on Setting up custom fields needed for the Ocean Premium platform in Current RMS

## Table of Content

|                                                                              |
|------------------------------------------------------------------------------|
| 0. [A word on Custom fields format](#markdown-header-a-word-on-custom-fields-format)|
| 1. [Set up product configurations](Set%20up%20product%20configurations)|
| 2. [Set up product descriptions](#markdown-header-product-descriptions)|
| 3. [Set up product images](#markdown-header-product-images)|
| 4. [Upload product images](#markdown-header-upload-product-images)|
| 5. [Configuring Accessories](#markdown-header-configuring-accessories)|

## A word on Custom fields format

We have setup custom fields that need to be of the following format, below some _examples_:

## Custom product configurations

- `custom_product_config_options_<specific_option>`

## Custom product descriptions

- `custom_product_descriptions_<specific_option>`

***Note***: _if you deviate from it, the setup of the custom fields and the frontend will ***not*** work!_


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

## Product images

This section describes adding **public icon custom fields** to the "Product" module.

To be able to display custom images for each product other than the one used inside CurrentRMS, 2 custom fields for public icon url need to be made:

* 3.1 Add a `Custom Field Group` named `custom_product_public_icon`

- System Setup -> Custom Field Groups -> Add Custom Field Group
- Name it `custom_product_public_icon`

![12.png](https://bitbucket.org/repo/qEd965M/images/1480953562-12.png)

* 3.2 Add ```custom_product_public_icon_url``` **custom fields** to the **Product** module

- System Setup -> Custom Field -> Add Custom Field
- set name to ```custom_product_public_icon_url```
- choose module ```Product```
- choose the custom field group ```custom_product_public_icon```
- set the **order** to 0
- choose field type ```String```

![13.png](https://bitbucket.org/repo/qEd965M/images/2482269974-13.png)

* 3.3 Add `custom_product_public_icon_thumb_url` **custom fields** to the **Product** module

- System Setup -> Custom Field -> Add Custom Field
- set name to `custom_product_public_icon_thumb_url`
- choose module `Product`
- choose the custom field group `custom_product_public_icon`
- set the **order** to `1`
- choose field type `String`

![14.png](https://bitbucket.org/repo/qEd965M/images/3815600737-14.png)

## Upload product images

This section describes uploading **public icon and icon thumb** to AWS S3 bucket for each product.

Now that the `custom_product_public_icon_url` and `custom_product_public_icon_thumb_url` fields are created, they can be populated with **image url from AWS S3 bucket**. S3 is the file storage service of AWS, where you can upload and download uploaded files, in this case we upload product images to AWS S3, these images will then be accessible by a **url string**.

* 4.1 Upload product image

- Log in to ocean premium AWS Management Console with your valid credentials 
(https://oceanpremium.signin.aws.amazon.com/console) (Account ID or alias = oceanpremium)

- Once logged in, type `S3` in the **Find Services** input field and press `Enter`

![15.png](https://bitbucket.org/repo/qEd965M/images/24151003-15.png)

![16.png](https://bitbucket.org/repo/qEd965M/images/1564715802-16.png)

- Inside the **S3 buckets** view, you see a list of all buckets created by us, unless instructed by us, **DO NOT CHANGE ANY SETTINGS**

- Click on the bucket `ocean-premium-public`, then `currentrms` -> `product-images` -> `public`

- Inside this folder you see a couple of images uploaded by us for testing purpose

![18.png](https://bitbucket.org/repo/qEd965M/images/2021069110-18.png)

    - You can upload pictures inside this folder directly if you want. But we suggest using a systematic naming strategy: First create a folder with the name that corresponds with the product ID, which can be derived from the currentRMS url. 

For example: for the product Seabob F5, the id is `148`

![20.png](https://bitbucket.org/repo/qEd965M/images/2117638500-20.png)

![21.png](https://bitbucket.org/repo/qEd965M/images/3309557532-21.png)

![22.png](https://bitbucket.org/repo/qEd965M/images/3789644213-22.png)

- Click on the created folder

- Click on **Upload** -> **Add files**

![23.png](https://bitbucket.org/repo/qEd965M/images/3494105478-23.png)

- Keep clicking **Next** and leave all settings **UNCHANGED** and finally on **Upload**

- Once the files are uploaded, click on it, and copy the **Object URL**

![24.png](https://bitbucket.org/repo/qEd965M/images/3952421003-24.png)

- Paste it on either `custom_product_public_icon_url` and  `custom_product_public_icon_thumb_url` in the product detail in CurrentRMS

![24-5.png](https://bitbucket.org/repo/qEd965M/images/3842950623-24-5.png)

- Repeat this process for all products that have images

# Configuring accessories

This section describes setting **Accessories Items** to **Accessory Only**.

Products may have accessories. To prevent accessory items to show up in the search, mark accessory items as **ACCESSORY ONLY** in **Edit Product** page inside CurrentRMS

![25.png](https://bitbucket.org/repo/qEd965M/images/403292708-25.png)