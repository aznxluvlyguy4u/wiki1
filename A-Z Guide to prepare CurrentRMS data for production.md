# A to Z guide 

This section describes on setting up custom fields needed for the Ocean Premium platform in Current RMS
and how to import data export files.


# End result after following this guide:

**Every product**  in Current RMS **must have** the following **minimum** properties set:

_- Mandatory means: It **must have**_

_- Optional means: It **may have**_

- (Mandatory) A product name
- (Mandatory) A SEO friendly product name
- (Mandatory) A full product description
- (Mandatory) A pulic friendly image
- (Mandatory) A rate to show in the rental frontend


## Table of Content

|                                                                              |
|------------------------------------------------------------------------------|
| 0. [A word on Custom fields format](#markdown-header-a-word-on-custom-fields-format)|
| 1. [(Optional) Set up product configurations](Set%20up%20product%20configurations)|
| 2. [(Mandatory) Set up product descriptions](Product%20descriptions)|
| 3. [(Mandatory) Set up product rates](Product%20rates)|
| 4. [(Mandatory) Set up product images](Product%20images)|
| 5. [(Mandatory) Upload product images](Product%20images#markdown-header-upload-product-images)|
| 6. [(Mandatory) Configuring Accessories](Configuring%20accessories)|
| 7. [Procedure of importing exported data files](Data%20import%20in%20CurrentRMS) |

## A word on Custom fields format

We have setup custom fields that need to be of the following format, below some _examples_:

## Custom product configurations

- `custom_product_config_options_<specific_option>`

## Custom product descriptions

- `custom_product_descriptions_<specific_option>`

***Note***: _if you deviate from it, the setup of the custom fields and the frontend will ***not*** work!_