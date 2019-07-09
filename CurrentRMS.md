# [Current RMS](https://oceanpremium-staging.current-rms.com)

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

## Current RMS - Staging - TRIAL ACCOUNT

The Staging environment of Current RMS: https://oceanpremium-staging.current-rms.com is **a trial account**, this is because ocean premium does not want to pay for the staging environment and has an arrangement with Current RMS to reset trial account, when the trial period ends.

In order to extend the trial period, [Frans Godschalk](mailto:frans@jongensvantechniek.nl) (JVT)
and [Janez Jezersek](mailto:jj@oceanpremium.com) (Ocean Premium) need to know when the trial period ends
and will manually extend the trial account. Instruct them to actively extend the trial period, BEFORE IT ENDS, otherwise the whole platform for the staging env will not work.


### Credentials

See [LastPass](https://lastpass.com) for the credentials to access the Current RMS account and API (token).

*Note:* If the credentials are not yet shared with you on [LastPass](http://lastpass.com), ask Frans or Steve.

### Data import

The staging environment acts as mirrored environment for production. The existing production environment is currently used by Ocean Premium. In order to get data exports from Production imported into Staging, go here to find the latest data dumps on [OneDrive](https://shopix99-my.sharepoint.com/:f:/g/personal/peter_jongensvantechniek_nl/Ehv7OJ-IWJNFmvLCQRWV2LoB2OPAe5SJbudzKu6Y_GB0oQ?e=kWnVST)

The data dumps are provided by Ocean Premium, if you need data dumps, other then the already provided dumps on OneDrive, you can contact the following persons (in the following contact order):

- [Frans Godschalk](mailto:frans@jongensvantechniek.nl) (JVT)
- [Janez Jezersek](mailto:jj@oceanpremium.com) (Ocean Premium)
- [Barbara Jezersek](mailto:barbara@oceanpremium.com) (Ocean Premium)

### Procedure
[See here for procedure](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Data%20import%20in%20CurrentRMS)


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

- See the [Postman collection & environment properties](API%20docs) for importing the collection into [Postman](https://www.getpostman.com)

- See the [API Request Examples](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Current%20RMS%20API%20request%20examples) for query parameter build up examples