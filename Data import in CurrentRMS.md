# Data import procedure

- [Staging environment](https://oceanpremium-staging.current-rms.com/)

## Importing csv's

- Login to Current RMS

    * Production: [https://xxx.current-rms.com](https://xxx.current-rms.com)

    * Staging: [https://oceanpremium-staging.current-rms.com](https://oceanpremium-staging.current-rms.com)

- Make sure the language setting of your account is set to: `Engles - United Kingdom`

_Note: that you also make sure that to set the `Rate definition` to: `Daily Rate (for now)`_

- Go to the data import section:

https://oceanpremium-staging.current-rms.com/imports/new?rp=/admin

- Import csv's in the following order:

**Notes:**
For all following imports, make sure you unselect the ID column, because the ID fields will be regenerated every time

![Screenshot from 2019-07-29 12-22-09.png](https://bitbucket.org/repo/qEd965M/images/2126575434-Screenshot%20from%202019-07-29%2012-22-09.png)

1. contacts

2. venues

3. organizations? (
    * first add Oraganisation Tax Class `0% IBEU` in System Setup -> Organisation Tax Classes,
    * add Organisation Tax Class `0% ICP`,
    * add custom field group `yacht` in System Setup -> Custom Field Groups,
    * add custom field `yacht` to organizations in System Setup -> Custom Fields

![Screenshot from 2019-07-29 13-18-47.png](https://bitbucket.org/repo/qEd965M/images/35234584-Screenshot%20from%202019-07-29%2013-18-47.png)

    * make sure a user account with the name `Barbara Jezersek` exists in System Setup -> Users
    * make sure a user account with the name `Blaz Oblak` exists in System Setup -> Users
    * then import organisation export file
)

4. vehicles

5. product groups

6. products (
    * system setup -> revenue groups -> add `Sale of goods`
    * system setup -> cost groups -> add `Logistics - Rental`
    * make sure a Product Tax Class exists with the name `Default` in System Setup -> Product Tax Classes
    * make sure a Product Tax Class exists with the name `VAT 22%` in System Setup -> Product Tax Classes
    * Add a Custom Field Group, named `custom_product_config_options`:
    * Add `custom_product_config_option_color` in System Setup -> List of Values -> Add List of Values
    * Add `custom_product_config_option_color` in System Setup -> Custom Field -> Add Custom Field
    * Add custom_product_description_seo_title
    * Add custom_product_description_head_1
    * Add custom_product_description_paragraph_1
    * Add custom_product_description_head_2
    * Add custom_product_description_paragraph_2
    * Add custom_product_description_head_3
    * Add custom_product_description_paragraph_3
    * Add custom_product_description_head_4
    * Add custom_product_description_paragraph_4
    * Add custom_product_description_head_5
    * Add custom_product_description_paragraph_5
    * Add custom_product_description_head_6
    * Add custom_product_description_paragraph_6
    * Add custom_product_description_head_7
    * Add custom_product_description_paragraph_7
    * Add custom_product_description_head_8
    * Add custom_product_description_paragraph_8
    * Add custom_product_description_head_9
    * Add custom_product_description_paragraph_9
    * Add custom_product_description_dimensions
    * import products export csv
)

11. accessories

12. add following stores in system setup -> stores:
    * Palma de Mallorca (NG)
    * S/Y ECHELON
    * M55
    * Monaco
    * Inchcape Shipping Services
    * M/Y OCEAN PARADISE
    * St. Maarten (DSM)
    * Athens (H360)
    * Fort Lauderdale (YC)
    * Maldives
    * Napoli (MLF)
    * Olbia (NA)
    * Antigua (AC)
    * MAREMOTO
    * M/Y GLADIATOR
13. stock level
14. rate (already exists)
15. serialized components (empty)
16. product supplier cost
17. add following values to service type in system System Setup > List of Values (
    * Handling
    * Shipping
18. add following values to revenue group in System Setup -> Revenue Group (
    * Logistics - Rental
19. services
20. service supplier cost (empty)
21. add a new Contact with the name "Blaz Oblak" and mark it as bookable resource
22. service resource