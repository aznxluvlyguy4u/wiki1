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

**Missing instructions:**

Results in:

```
Row	Error
2	Could not find a Contact with an id of 263
3	Could not find a Contact with an id of 161
...
```

**TODO: Add complete instructions documentation**

2. venues

**Missing instructions:**

```
Your upload of Venue data from file 'Current-Venue-20190724-16549-1h46xhj.csv' has failed with the following errors: 

Row	Error
2	Could not find a Venue with an id of 344
3	Could not find a Venue with an id of 374
```

3. organizations? (
    * first add Oraganisation Tax Class `0% IBEU` in System Setup -> Organisation Tax Classes,
    * add Oraganisation Tax Class `0% ICP`,
    * add custom field group `yacht` in System Setup -> Custom Field Groups,
    * add custom field `yacht` to organizations in System Setup -> Custom Fields

![Screenshot from 2019-07-29 13-18-47.png](https://bitbucket.org/repo/qEd965M/images/35234584-Screenshot%20from%202019-07-29%2013-18-47.png)

    * make sure a user with the name `Barbara Jezersek` exist in System Setup -> Users
    * then import organisation export file
)

**TODO: Add complete instructions documentation**

4. vehicles

**Missing instructions:**

Results in:

```
Upload Results
The upload failed with the following errors.


Row	Error
2	Could not find a Vehicle with an id of 96
3	Could not find a Vehicle with an id of 24
4	Could not find a Vehicle with an id of 25
```

**TODO: Add complete instructions documentation**

5. product groups

**Missing instructions:**

Results in:

```
Upload Results
The upload failed with the following errors.


Row	Error
2	Could not find a Product Group with an id of 169
3	Could not find a Product Group with an id of 158
4	Could not find a Product Group with an id of 162
5	Could not find a Product Group with an id of 164
6	
```

**TODO: Add complete instructions documentation**

6. system setup -> revenue groups -> add 'Sale of goods'
7. system setup -> cost groups -> add 'Logistics - Rental'
8. change products.csv row 117 Pontoon Sockets for Schiller Bike image url from :

    * 'https://s3.amazonaws.com/current-rms/86743260-d606-0136-9f37-0a9ca217e95b/icons/305/original/schiller-pontton-socket.jpg'

    * temporary to:

    * 'https://s3.amazonaws.com/current-rms/86743260-d606-0136-9f37-0a9ca217e95b/icons/238/original/schiller-pontoon.jpg'

10. products

**Missing instructions:**

Results in:

```
Your upload of Product data from file 'Current-Product-20190724-16549-889mu3.csv' has failed with the following errors: 


Row	Error
2	Could not find a Product with an id of 162
3	Could not find a Product with an id of 267
```

and

```

Row	Error
2	Could not find the Tax Class using 'Default'
3	Could not find the Tax Class using 'Default'
4	Could not find the Tax Class using 'Default'
5	Could not find the Tax Class using 'Default'
6	Could not find the Tax Class using 'VAT 22%'
```
**TODO: Add complete instructions documentation**

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