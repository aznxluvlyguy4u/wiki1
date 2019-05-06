# Data import procedure

- [Staging environment](https://oceanpremium-staging.current-rms.com/)

## Importing csv's

- Login to Current RMS and go to the data import section:

https://oceanpremium-staging.current-rms.com/imports/new?rp=/admin

- Import csv's in the following order:

1. contacts
2. venues
3. organizations? (add Sale Tax Class '0% IBEU', '0% ICP', add custom field group yacht, add custom field yacht)
4. vehicles
5. product groups
6. system setup -> revenue groups -> add 'Sale of goods'
7. system setup -> cost groups -> add 'Logistics - Rental'
8. change products.csv row 117 Pontoon Sockets for Schiller Bike image url from :

  'https://s3.amazonaws.com/current-rms/86743260-d606-0136-9f37-0a9ca217e95b/icons/305/original/schiller-pontton-socket.jpg'

temporary to:

  'https://s3.amazonaws.com/current-rms/86743260-d606-0136-9f37-0a9ca217e95b/icons/238/original/schiller-pontoon.jpg'

9. products
10. accessories
11. add stores in system setup -> stores
12. stock level
13. rate (already exists)
14. serialized components (empty)
15. product supplier cost
16. add service type in system System Setup > List of Values (Handling, Shipping)
17. add revenue group in System Setup -> Revenue Group (Logistics - Rental)
18. services
19. service supplier cost 
20. service resource