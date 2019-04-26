# Current RMS

## Table of Content

| Table of Content                                                             |
|------------------------------------------------------------------------------|
| 0. [Contact / Helpdesk](#markdown-header-contact-currentrms)                 |
| 1. [Staging environment](#markdown-header-staging-environment)               |
| 2. [Credentials](#markdown-header-credentials)                       |
| 3. [Data Import](#markdown-header-data-import)                               |
| 4. [API](#markdown-header-api)                                               |

This API serves as a proxy to [Current RMS](https://current-rms.com).

### Contact CurrentRMS

We have a contact person for technical questions concerning Current RMS (platform / API), in the following contact order):

- [Matthew Finkel](mailto:matthew.finkel@current-rms.com)
- [help@current-rms.com](mailto:help@current-rms.com)

### Staging environment

*Staging:* https://oceanpremium-staging.current-rms.com

*Current RMS - API Docs:* https://api.current-rms.com/doc

### Credentials

See [LastPass] for the credentials to access the Current RMS account and API (token).
If the credentials are not yet shared with you on LastPass, ask Frans or Steve.

### Data import

The staging environment acts as mirrored environment for production. The existing production environment is currently used by Ocean Premium. In order to get data exports from Production imported into Staging, go here to find the latest data dumps on OneDrive:

https://shopix99-my.sharepoint.com/:f:/g/personal/peter_jongensvantechniek_nl/Ehv7OJ-IWJNFmvLCQRWV2LoB2OPAe5SJbudzKu6Y_GB0oQ?e=kWnVST

The data dumps are provided by Ocean Premium, if you need data dumps, other then the already provided dumps on OneDrive, you can contact the following persons (in the following contact order):

- [Frans Godschalk](mailto:frans@jongensvantechniek.nl) (JVT)
- [Janez Jezersek](mailto:jj@oceanpremium.com) (OP)
- [Barbara Jezersek](mailto:barbara@oceanpremium.com) (OP)

### API 

#### Request
Here is an example utilizing _curl_ to do a request to the Current RMS API on the _stores_  endpoint.

See the [Current RMS - API Docs](https://api.current-rms.com/doc) for more information on available endpoints.

See [credentials](#markdown-header-credentials) for the API token.

```shell
$ curl --header "X-SUBDOMAIN:oceanpremium-staging" --header "X-AUTH-TOKEN:<TOKEN>" /
 "https://api.current-rms.com/api/v1/stores" | python -m json.tool
```

#### Response

```json
{
    "stores": [
        {
            "id": 1,
            "country_id": 8,
            "region_id": 1,
            "name": "Default",
            "street": "Jupiter 65",
            "city": "Poeldijk",
            "county": "ZH",
            "postcode": "2685 LV",
            "created_at": "2019-03-12T09:56:39.373Z",
            "updated_at": "2019-03-12T09:56:39.373Z",
            "country": {
                "id": 8,
                "name": "Netherlands",
                "code": "NL",
                "has_state_tax": false,
                "eu_member": true,
                "currency_code": "EUR"
            },
            "icon": null
        }
    ],
    "meta": {
        "total_row_count": 1,
        "row_count": 1,
        "page": 1,
        "per_page": 20
    }
}
```