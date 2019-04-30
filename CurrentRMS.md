# [Current RMS](https://current-rms.com)

The Ocean Premium - REST API serves as a proxy to [Current RMS](https://current-rms.com).

## Table of Content

|                                                                              |
|------------------------------------------------------------------------------|
| 0. [Contact / Helpdesk](#markdown-header-contact-currentrms)                 |
| 1. [Environments](#markdown-header-environments)                             |
| 2. [Credentials](#markdown-header-credentials)                               |
| 3. [Data Import](#markdown-header-data-import)                               |
| 4. [API](#markdown-header-api)                                               |


### Contact CurrentRMS

We have a contact person for technical questions concerning Current RMS (platform / API), in the following contact order):

- [Matthew Finkel - matthew.finkel@current-rms.com](mailto:matthew.finkel@current-rms.com)
- [CurrentRMS Helpdesk - help@current-rms.com](mailto:help@current-rms.com)

### Environments

|                                                                              | 
|------------------------------------------------------------------------------|
| 0. Staging:  https://oceanpremium-staging.current-rms.com                    |                                                
| 1. API Docs: https://api.current-rms.com/doc                                 |

### Credentials

See [LastPass](https://lastpass.com) for the credentials to access the Current RMS account and API (token).

*Note:* If the credentials are not yet shared with you on [LastPass](http://lastpass.com), ask Frans or Steve.

### Data import

The staging environment acts as mirrored environment for production. The existing production environment is currently used by Ocean Premium. In order to get data exports from Production imported into Staging, go here to find the latest data dumps on [OneDrive](https://shopix99-my.sharepoint.com/:f:/g/personal/peter_jongensvantechniek_nl/Ehv7OJ-IWJNFmvLCQRWV2LoB2OPAe5SJbudzKu6Y_GB0oQ?e=kWnVST)

The data dumps are provided by Ocean Premium, if you need data dumps, other then the already provided dumps on OneDrive, you can contact the following persons (in the following contact order):

- [Frans Godschalk](mailto:frans@jongensvantechniek.nl) (JVT)
- [Janez Jezersek](mailto:jj@oceanpremium.com) (Ocean Premium)
- [Barbara Jezersek](mailto:barbara@oceanpremium.com) (Ocean Premium)


Data import procedure:
import csv's in the following order:

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


#### JVT & Ocean Premium responsibilities

As discussed in a meeting (26-04-2019) with Ocean Premium (Janez & Barbara), Ocean Premium & JVT will take responsibility for the following concerns.

##### Ocean Premium

- Make sure all data (products / accessories / stores, ect.) are correctly prepared and setup, linked and entity details provided, to make it properly function in Current RMS.

- Will conform to configurations JVT made in Current RMS on production environment (in terms of additions / Custom Fields, ect)

##### Jongens van Techniek

- In case custom fields / additions / configurations made in Current RMS that needs to be replicated on the production environment, JVT will document and communicate it with Ocean Premium.

- JVT will contact CurrentRMS if we have questions concerning CurrentRMS that are not easily answered, see [here](#markdown-header-contact-currentrms)

### API 

- See [credentials](#markdown-header-credentials) for the API token.

- See the [Current RMS - API Docs](https://api.current-rms.com/doc) for more information on available endpoints.

- See the [Postman collection & environment properties](https://shopix99-my.sharepoint.com/:f:/g/personal/peter_jongensvantechniek_nl/En6dO8Va9JhKiBVCDXwMm5kBT2XWuxPIUK0cb4hjGkhE9w?e=RMll9Y) for importing the collection into [Postman](https://www.getpostman.com)