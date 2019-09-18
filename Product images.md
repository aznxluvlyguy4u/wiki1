## Preparing images

This section describes on how to prepare image for products.

### Mandatory image sizes

- Make sure you have prepared the _FULL SIZE_ image and the _THUMBNAIL size_ image

- Make sure the ratio of the image (width and height) are ALWAYS the same (thus for any image, for any product) 
  

This means: 

- Product A has an image size for the FULL Size image, lets say 300 x 300 pixels (this is an example, you may choose larger, but maintain ratio)

- Product A has an image size for the THUMBNAIL Size image, lets say 100 x 100 pixels (this is an example, you may choose larger, but maintain ratio)

Then ***any*** Product X has the same size for FULL and Thumbnail image, ratio of 300 x 300 (FULL) and 100 x 100 (THUMB)

Thus, there will ALWAYS be:

- 1 format and thus ratio of an image for FULL size 
- 1 format and thus ratio of an image for THUMB size


### Mandatory image format

- Any image needs to be of the `PNG` format
- DO NOT MIX PNG and JPEG images

This means ***any*** Product X image is of type `PNG`


## Product & Product group images

This section describes adding **public icon custom fields** to the "Product" and "Product Groups" modules.

To be able to display custom images for each _product_ and for each _product group_, other than the one used inside CurrentRMS, 2 custom fields for public icon url need to be made:


![12.png](https://bitbucket.org/repo/qEd965M/images/1480953562-12.png)


#### Product images

##### public_icon_url

- System Setup -> Custom Field -> Add Custom Field
- set name to ```public_icon_url```
- choose module ```Product```
- choose the custom field group ```custom_product_public_icon```
- set the **order** to 0
- choose field type ```String```

##### public_icon_thumb_url

- System Setup -> Custom Field -> Add Custom Field
- set name to ```public_icon_thumb_url```
- choose module ```Product```
- choose the custom field group ```custom_product_public_icon```
- set the **order** to 0
- choose field type ```String```


#### Product groups images

##### public_icon_url

- System Setup -> Custom Field -> Add Custom Field
- set name to ```public_icon_url```
- choose module ```Product Groups```
- choose the custom field group ```custom_product_public_icon```
- set the **order** to 0
- choose field type ```String```

##### public_icon_thumb_url

- System Setup -> Custom Field -> Add Custom Field
- set name to ```public_icon_thumb_url```
- choose module ```Product Groups```
- choose the custom field group ```custom_product_public_icon```
- set the **order** to 0
- choose field type ```String```


![13.png](https://bitbucket.org/repo/qEd965M/images/2482269974-13.png)

* 3.3 Add `public_icon_thumb_url` **custom fields** to the **Product** module

- System Setup -> Custom Field -> Add Custom Field
- set name to `public_icon_thumb_url`
- choose module `Product`
- choose the custom field group `custom_product_public_icon`
- set the **order** to `1`
- choose field type `String`

![14.png](https://bitbucket.org/repo/qEd965M/images/3815600737-14.png)


## Upload product images

This section describes uploading **public icon and icon thumb** to AWS S3 bucket for each product. 

Now that the `public_icon_url` and `public_icon_thumb_url` fields are created, they can be populated with **image url from AWS S3 bucket**. S3 is the file storage service of AWS, where you can upload and download uploaded files, in this case we upload product images to AWS S3, these images will then be accessible by a **url string**.

* 4.1 Upload product image

- Log in to ocean premium AWS Management Console with your valid credentials 
(https://oceanpremium.signin.aws.amazon.com/console) (Account ID or alias = oceanpremium)

- Once logged in, type `S3` in the **Find Services** input field and press `Enter`

![15.png](https://bitbucket.org/repo/qEd965M/images/24151003-15.png)

![16.png](https://bitbucket.org/repo/qEd965M/images/1564715802-16.png)

- Inside the **S3 buckets** view, you see a list of all buckets created by us, unless instructed by us, **DO NOT CHANGE ANY SETTINGS**

#### Product images

- Click on the bucket `ocean-premium-public`, then `currentrms` -> `product-images` -> `public`

#### Product Group images

- Click on the bucket `ocean-premium-public`, then `currentrms` -> `product-group-images` -> `public`

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

Make sure that the FULL AND THUMBNAIL image are prepared and ready for upload

- Keep clicking **Next** and leave all settings **UNCHANGED** and finally on **Upload**

- Once the files are uploaded, click on it, and copy the **Object URL**

![24.png](https://bitbucket.org/repo/qEd965M/images/3952421003-24.png)

##### Product Image / Product Group Image

##### Product

- Go the the product edit page in CurrentRMS of the concerning product to add images to, for example:

    * https://oceanpremium.current-rms.com/products/20/edit?rp=%2Fproducts%2F20

##### Product Group

- Go the the product group edit page in CurrentRMS of the concerning group to add images to:

    * Go to `System Setup` -> `Product Groups`, select the group to edit, for example:

        - https://oceanpremium.current-rms.com/product_groups?rp=/admin

        - https://oceanpremium.current-rms.com/product_groups/169/edit


###### Pasting Image URL's

- Paste the URL of the FULL IMAGE in the `public_icon_url` field

- Paste the URL of the THUMBNAIL IMAGE in the `public_icon_thumb_url` 


***NOTE***, ***ALWAYS*** fill in both the `public_icon_url ` AND the `public_icon_thumb_url`. If you leave one of them blank the custom images will ***NOT*** be visible in the frontend! 

![24-5.png](https://bitbucket.org/repo/qEd965M/images/3842950623-24-5.png)

- Repeat this process for all products / product groups that have images