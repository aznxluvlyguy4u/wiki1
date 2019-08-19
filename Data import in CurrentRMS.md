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

`System setup -> Import Data -> Current-Contact.csv`

### Import venues

`System setup -> Import Data -> Current-Venues.csv`

- Set _locality_ and _postalcode_

![Screenshot 2019-08-19 at 12.50.23.png](https://bitbucket.org/repo/qEd965M/images/2414019052-Screenshot%202019-08-19%20at%2012.50.23.png)

### Import Organizations

- First add Organisation Tax Class `0% IBEU`:
  `System Setup -> Organisation Tax Classes`

- Add Organisation Tax Class `0% ICP`

- Add custom field group `yacht`

`System Setup -> Custom Field Groups, (STILL NEEDED?)`

- Add custom field `yacht` to organisations

`System Setup -> Custom Fields`

![Screenshot from 2019-07-29 13-18-47.png](https://bitbucket.org/repo/qEd965M/images/35234584-Screenshot%20from%202019-07-29%2013-18-47.png)

- Create user account with the name `Barbara Jezersek (barbara@oceanpremium.com)` exists: 
`System Setup -> Users`

- Create user account with the name `Blaz Oblak (blaz@oceanpremium.com)` exists: `System Setup -> Users`

- `System setup -> Import Data -> Current-Organisation.csv`

- Set _locality_ and _postalcode_

![Screenshot 2019-08-19 at 12.50.23.png](https://bitbucket.org/repo/qEd965M/images/2414019052-Screenshot%202019-08-19%20at%2012.50.23.png)

### Import Vehicles

`System setup -> Import Data -> Current-Vehicles.csv`

### Import Product groups

`System setup -> Import Data -> Current-Product-Groups.csv`

### Import Product 

`System setup -> Import Data -> Current-Product.csv`

### Revenue groups 

`System setup -> revenue groups -> add Sale of goods` 

### Cost groups

`System setup -> cost groups -> add Logistics - Rental`

- Make sure a Product Tax Class exists with the name `Default` in System Setup -> Product Tax Classes

- Make sure a Product Tax Class exists with the name `VAT 22%` in System Setup -> Product Tax Classes


### Custom Fields

- [See here for tutorial for adding custom fields to product module](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Product%20descriptions)

Add the following Custom Fields Group to `System Setup -> Custom Field groups`:

 * `custom_product_config_options`

 * `custom_product_config_option_color` in: `System Setup -> List of Values -> Add List of Values`

 * `custom_product_config_option_color` in: `System Setup -> Custom Field -> Add Custom Field`

 * `custom_product_description_seo_title`

 * `custom_product_description_dimensions`

Repeat the following for **1 to 9 (including) **, by replacing `x`:

For example: `custom_product_paragraph_9` / `custom_product_description_head_9`

 * `custom_product_description_paragraph_x`
 * `custom_product_description_head_x`


### Import accessories

`System setup -> Import Data -> Current-Accessory.csv`

### Import Stores

Add following stores in system setup -> stores ( Or make sure they exist in currentRMS):

Total stores: 36

```
Antibes
Antigua (AC)
Athens (360)
Athens (Sotiris)
BCM (Kotor)
Corfu
Default
Dubrovnik (BWA)
Dubrovnik (Kristijan)
Fort Lauderdale (YC)
Genova (Maremoto)
Ibiza (Rodriquez)
Inchcape Shipping Services
JVT
Kos (A1)
M55
Male
Maldives
Malta
M/Y GLADIATOR
M/Y OCEAN PARADISE
Napoli (MLF)
New Items Store
Olbia (NA)
Olbia (SYS)
Palermo (Artemis)
Palma de Mallorca (ED)
Palma de Mallorca (NG)
Rhodes (Roditis)
Riposto (Artemis)
Split (Luka)
St. Maarten (DSM)
S/Y ECHELON
Tivat (BWA)
Venice (Katarina)
Zadar (Alessia)
```

### Import Stock level

`System setup -> Import Data -> Current-StockLevel.csv`

If an error occurs like below, one can ignore the error:

```
A 'Bulk Stock' stock level already exists for the product, store and stock type.
```




### Import Rate

- Already exists

`System setup -> Import Data -> Current-Rate.csv`


If an error occurs like below, one can ignore the error:

```
A rate for this product, store and transaction type already exists with a blank from/to period.
```

### Serialized components (OBSOLETE / SKIP)

- Empty

- Note that due to breaking in Current RMS - introduced around first week of August 2019, this component is either changed by name or removed by Current RMS

- This exported file can be ignored

- OBSOLETE - `System setup -> Import Data -> Current-SerializedComponent.csv`


### Import Product supplier cost

- Empty

`System setup -> Import Data -> Current-ProductSupplierCost.csv`

### Service types

-  `System System Setup > List of Values: 'Handling', 'Shipping'`

### Revenue Group

-  `System Setup -> Revenue Group: Logistics - Rental`

### Import Service supplier cost

- Empty

`System setup -> Import Data -> Current-ServiceSupplierCost.csv`

### Service resource

`System setup -> Import Data -> Current-ServiceResource.csv`