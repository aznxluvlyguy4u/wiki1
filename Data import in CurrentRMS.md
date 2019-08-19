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

### Import contacts

### Import venues

- Set _locality_ and _postalcode_

![Screenshot 2019-08-19 at 12.50.23.png](https://bitbucket.org/repo/qEd965M/images/2414019052-Screenshot%202019-08-19%20at%2012.50.23.png)

### Import Organizations

- first add Organisation Tax Class `0% IBEU`:
  `System Setup -> Organisation Tax Classes`

- Add Organisation Tax Class `0% ICP`

- Add custom field group `yacht`

`System Setup -> Custom Field Groups, (STILL NEEDED?)`

- Add custom field `yacht` to organisations

`System Setup -> Custom Fields`

* ![Screenshot from 2019-07-29 13-18-47.png](https://bitbucket.org/repo/qEd965M/images/35234584-Screenshot%20from%202019-07-29%2013-18-47.png)

- Create user account with the name `Barbara Jezersek (barbara@oceanpremium.com)` exists: 
`System Setup -> Users`

- Create user account with the name `Blaz Oblak (blaz@oceanpremium.com)` exists: `System Setup -> Users`

### Import organisation 

- Set _locality_ and _postalcode_

![Screenshot 2019-08-19 at 12.50.23.png](https://bitbucket.org/repo/qEd965M/images/2414019052-Screenshot%202019-08-19%20at%2012.50.23.png)

### Import Vehicles

### Import Product groups

### Import Product 

### System setup -> revenue groups -> add `Sale of goods`

### System setup -> cost groups -> add `Logistics - Rental`

- Make sure a Product Tax Class exists with the name `Default` in System Setup -> Product Tax Classes

- Make sure a Product Tax Class exists with the name `VAT 22%` in System Setup -> Product Tax Classes

- [See here for tutorial for adding custom fields to product module](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Product%20descriptions)

- Add the following Custom Fields Group to `Custom Field groups`

 * OPTIONAL `custom_product_config_options`

 * OPTIONAL `custom_product_config_option_color` in: `System Setup -> List of Values -> Add List of Values`

 * OPTIONAL `custom_product_config_option_color` in: `System Setup -> Custom Field -> Add Custom Field`

 * `custom_product_description_seo_title`

 * `custom_product_description_head_1`

Repeat the following for **1 to 9**, by replacing `x`:

For example: `custom_product_paragraph_9` / `custom_product_description_head_9`


 * `custom_product_description_paragraph_x`
 * `custom_product_description_head_x`

---

 * `custom_product_description_dimensions`

Import products export csv


11. accessories

12. add following stores in system setup -> stores ( Or make sure they exist in currentRMS) :

    * Antibes
    * Antigua (AC)
    * Athens (360)
    * Athens (Sotiris)
    * BCM (Kotor)
    * Corfu
    * Default
    * Dubrovnik (BWA)
    * Dubrovnik (Kristijan)
    * Fort Lauderdale (YC)
    * Genova (Maremoto)
    * Ibiza (Rodriquez)
    * Inchcape Shipping Services *?*
    * JVT
    * Kos (A1)
    * M55
    * Male
    * Maldives
    * Malta
    * M/Y GLADIATOR
    * M/Y OCEAN PARADISE
    * Napoli (MLF)
    * New Items Store
    * Olbia (NA)
    * Olbia (SYS)
    * Palermo (Artemis)
    * Palma de Mallorca (ED)
    * Palma de Mallorca (NG)
    * Rhodes (Roditis)
    * Riposto (Artemis)
    * Split (Luka)
    * St. Maarten (DSM)
    * S/Y ECHELON *?*
    * Tivat (BWA)
    * Venice (Katarina)
    * Zadar (Alessia)

13. stock level
14. rate (already exists)
15. serialized components (empty)
16. product supplier cost

17. services (
    * add following values to `service type` in system System Setup > List of Values (
        * Handling
        * Shipping
    * add following values to `revenue group` in System Setup -> Revenue Group (
        * Logistics - Rental
)
18. service supplier cost (empty)
19. service resource