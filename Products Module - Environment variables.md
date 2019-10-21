# Products Module - Environment variables

### IMPORTANT NOTES 

- See [LastPass](https://lastpass.com) for the values

- the `SENTRY_DSN` needs to be capitalised, in order to be picked up by the Sentry SDK*

- the `env` key can be: _prod_ or _dev_, when in `dev` the API will show FULL STACKTRACES when an error occurs, MAKE SURE TO set _env_ to `prod` when deploying to _production_ to not leak sensitive information.


## Spring / Intellij

- See [here](Run%20config%20setup) for setting up a Run configuration with environment variables in IntelliJ

```
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
dev_api_url=https://1qie0vagy1.execute-api.eu-west-1.amazonaws.com/dev/api/v1/products
staging_api_url=https://zu6wjlgc49.execute-api.eu-west-1.amazonaws.com/staging/api/v1/products
production_api_url=https://y9gnyonusf.execute-api.eu-west-1.amazonaws.com/prod/api/v1/products
SENTRY_DSN=https://<ID>@sentry.io/<ID>
stripe_secret_key=<SK_KEY_VALUE>
stripe_webhook_secret_key=<HSEC_KEY_VALUE>
env=dev
```


After the environment variables are setup, one can run the concerning run configuration to _locally_ run the API.


## Serverless / AWS lambda

- Create a `properties.json` file in the _root_ of the _products_ module

- Paste below contents and fill in values for given keys


```json
{
  "products":
  {
    "timezone":"Europe/Amsterdam",
    "slack": {
      "webhook_jvt": "<WEBHOOK_URL>",
      "webhook_op": "<WEBHOOK_URL>"
    },
    "current_rms": {
      "token": "<TOKEN_VALUE>",
      "subdomain": "<DOMAIN_VALUE>",
      "api_url": "https://api.current-rms.com/api/v1/"
    },
    "emailer": {
      "smtp_host": "email-smtp.eu-west-1.amazonaws.com",
      "username" : "<ACCESS_KEY_ID>",
      "password": "<SECRECT_KEY_ID>",
      "sender": "noreply@oceanpremium.com",
      "back_office": "<YOUR OR BACKOFFICE EMAIL ADRESS - FOR DEV - USE YOUR JVT ADDRESS>"
    },
    "sentry_dsn": "https://<ID>@sentry.io/<ID>",
    "env": "prod",
    "endpoints": {
      "dev": "https://1qie0vagy1.execute-api.eu-west-1.amazonaws.com/dev/api/v1/",
      "staging": "https://zu6wjlgc49.execute-api.eu-west-1.amazonaws.com/staging/api/v1/",
      "production": "https://y9gnyonusf.execute-api.eu-west-1.amazonaws.com/prod/api/v1/"
    },
    "stripe": {
      "secret_key": "sk_test_<TOKEN>",
      "webhook_secret_key": "whsec_<TOKEN>"
    }
  }
}
```

After the environment variables are setup in the _properties file_, one can run the deploy task for the concerning module.