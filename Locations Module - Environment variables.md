# Locations Module - Environment variables


### IMPORTANT NOTES 

- See [LastPass](https://lastpass.com) for the values

- the `SENTRY_DSN` needs to be capitalised, in order to be picked up by the Sentry SDK*

- the `env` key can be: _prod_ or _dev_, when in `dev` the API will show FULL STACKTRACES when an error occurs, MAKE SURE TO set _env_ to `prod` when deploying to _production_ to not leak sensitive information.

- take special notice of urls with *trailing* slashes, *those are not accidental*...

## Local 

- See [here](Run%20config%20setup) for setting up a Run configuration with environment variables in IntelliJ

```
SENTRY_DSN=<https://<ID>@sentry.io/ID>
slack_webhook_jvt=<WEBHOOK_URL>
slack_webhook_op=<WEBHOOK_URL>
current_rms_token=<TOKEN_VALUE>
current_rms_subdomain=<DOMAIN_VALUE>
current_rms_api_url=https://api.current-rms.com/api/v1/
emailer_smtp_host=email-smtp.eu-west-1.amazonaws.com
emailer_username=<ACCESS_KEY_ID>
emailer_password=<SECRECT_KEY_ID>
emailer_sender=noreply@oceanpremium.com
emailer_back_office=<YOUR OR BACKOFFICE EMAIL ADRESS - FOR DEV - USE YOUR JVT ADDRESS>
env=dev
```


After the environment variables are setup, one can run the concerning run configuration to _locally_ run the API.


## Remote

- Create a `properties.json` file in the _root_ of the **LOCATIONS** module

- Paste below contents and fill in values for given keys

- the `env` key can be: _prod_ or _dev_, when in `dev` the API will show FULL STACKTRACES when an error occurs, MAKE SURE TO set _env_ to `prod` when deploying to _production_ to not leak sensitive information.


```json
{
  "locations":
  {
    "timezone":"Europe/Amsterdam",
    "slack": {
      "webhook_jvt": "<WEBHOOK_URL>"
    },
    "current_rms": {
      "token": "<TOKEN_VALUE>",
      "subdomain": "<DOMAIN_VALUE>",
      "api_url": "https://api.current-rms.com/api/v1/"
    },
    "sentry_dsn": "<https://<ID>@sentry.io/ID>",
    "env": "prod"
  }
}
```

After the environment variables are setup in the _properties file_, one can run the deploy task for the concerning module.