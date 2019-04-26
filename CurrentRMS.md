# Current RMS

## Table of Content

|                                                                              |
|------------------------------------------------------------------------------|
| 0. [Contact / Helpdesk](#markdown-header-contact-currentrms)                 |
| 1. [Environments](#markdown-header-environments)                             |
| 2. [Credentials](#markdown-header-credentials)                               |
| 3. [Data Import](#markdown-header-data-import)                               |
| 4. [API](#markdown-header-api)                                               |

This API serves as a proxy to [Current RMS](https://current-rms.com).

### Contact CurrentRMS

We have a contact person for technical questions concerning Current RMS (platform / API), in the following contact order):

- [Matthew Finkel](mailto:matthew.finkel@current-rms.com)
- [help@current-rms.com](mailto:help@current-rms.com)

### Environments

|                                                                              | 
|------------------------------------------------------------------------------|
| 0. CurrentRMS - Staging:  https://oceanpremium-staging.current-rms.com       |                                                
| 1. CurrentRMS - API Docs: https://api.current-rms.com/doc)                   |

### Credentials

See [LastPass](https://lastpass.com) for the credentials to access the Current RMS account and API (token).

*Note:* If the credentials are not yet shared with you on LastPass, ask Frans or Steve.

### Data import

The staging environment acts as mirrored environment for production. The existing production environment is currently used by Ocean Premium. In order to get data exports from Production imported into Staging, go here to find the latest data dumps on [OneDrive](https://shopix99-my.sharepoint.com/:f:/g/personal/peter_jongensvantechniek_nl/Ehv7OJ-IWJNFmvLCQRWV2LoB2OPAe5SJbudzKu6Y_GB0oQ?e=kWnVST)

The data dumps are provided by Ocean Premium, if you need data dumps, other then the already provided dumps on OneDrive, you can contact the following persons (in the following contact order):

- [Frans Godschalk](mailto:frans@jongensvantechniek.nl) (JVT)
- [Janez Jezersek](mailto:jj@oceanpremium.com) (OP)
- [Barbara Jezersek](mailto:barbara@oceanpremium.com) (OP)

#### JVT & OP roles 


##### Ocean Premium
As discussed in a meeting (26-04-2019) with Ocean Premium (Janez & Barbara), OP will take responsibility for the following concerning Current RMS - Staging environment:

- Make sure all data (products / accessories / stores, ect.) are correctly prepared and setup, linked and entity details provided, to make it properly function in Current RMS.

- Will conform to configurations JVT made in Current RMS on production environment (in terms of additions / Custom Fields, ect)

##### CurrentRMS

As discussed in a meeting (26-04-2019) with Ocean Premium (Janez & Barbara), OP will take responsibility for the following concerning Current RMS - Staging environment:

- In case custom fields / additions / configurations made in Current RMS that needs to be replicated on the production environment, JVT will document and communicate it with OP.

- JVT will contact CurrentRMS if we have questions concerning CurrentRMS that are not easily answered, see [here](#markdown-header-contact-currentrms)

### API 

- See the [Current RMS - API Docs](https://api.current-rms.com/doc) for more information on available endpoints.


- See the [POSTman collection & environment properties]() for importing the collection into POSTman

See [credentials](#markdown-header-credentials) for the API token.