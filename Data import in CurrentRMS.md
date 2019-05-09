# Data import procedure

- [Staging environment](https://oceanpremium-staging.current-rms.com/)

## Importing csv's

- Login to Current RMS and go to the data import section:

https://oceanpremium-staging.current-rms.com/imports/new?rp=/admin

- Import csv's in the following order:

1. contacts
2. venues
3. organizations? (
  * first add Oraganisation Tax Class '0% IBEU' in System Setup -> Organisation Tax Classes,
  * add Oraganisation Tax Class '0% ICP',
  * add custom field group yacht in System Setup -> Custom Field Groups,
  * add custom field yacht to organizations in System Setup -> Custom Fields
)
4. vehicles
5. product groups
6. system setup -> revenue groups -> add 'Sale of goods'
7. system setup -> cost groups -> add 'Logistics - Rental'
8. change products.csv row 117 Pontoon Sockets for Schiller Bike image url from :

  'https://s3.amazonaws.com/current-rms/86743260-d606-0136-9f37-0a9ca217e95b/icons/305/original/schiller-pontton-socket.jpg'

temporary to:

  'https://s3.amazonaws.com/current-rms/86743260-d606-0136-9f37-0a9ca217e95b/icons/238/original/schiller-pontoon.jpg'

10. products
11. accessories
12. add stores in system setup -> stores
13. stock level
14. rate (already exists)
15. serialized components (empty)
16. product supplier cost
17. add service type in system System Setup > List of Values (Handling, Shipping)
18. add revenue group in System Setup -> Revenue Group (Logistics - Rental)
19. services
20. service supplier cost 
21. service resource