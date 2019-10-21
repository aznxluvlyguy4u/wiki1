# Products Module - Environment variables

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

## Serverless / AWS lambda

- Create a `properties.json` file in the _root_ of the _products_ module

- Paste below contents and fill in values for given keys, see [LastPass](https://lastpass.com) for values

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