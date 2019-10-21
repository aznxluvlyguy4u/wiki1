# Auth Module - Environment variables

### IMPORTANT NOTES 

- See [LastPass](https://lastpass.com) for the values

- the `SENTRY_DSN` needs to be capitalised, in order to be picked up by the Sentry SDK*

- the `env` key can be: _prod_ or _dev_, when in `dev` the API will show FULL STACKTRACES when an error occurs, MAKE SURE TO set _env_ to `prod` when deploying to _production_ to not leak sensitive information.

- take special notice of urls with *trailing* slashes, *those are not accidental*...

- Due to the auth module being the first module developed, the uniform format of environment variables was not yet set up

## Local 

- See [here](Run%20config%20setup) for setting up a Run configuration with environment variables in IntelliJ

- Set below variables for the **AuthDriver**:
 
```
SENTRY_DSN=<https://<ID>@sentry.io/ID>
SLACK_LOGGER_WEBHOOK=<WEBHOOK_URL>
```


After the environment variables are setup, one can run the concerning run configuration to _locally_ run the API.


## Remote

- Create a `properties.json` file in the _root_ of the **AUTH** module

- Paste below contents and fill in values for given keys

- the `env` key can be: _prod_ or _dev_, when in `dev` the API will show FULL STACKTRACES when an error occurs, MAKE SURE TO set _env_ to `prod` when deploying to _production_ to not leak sensitive information.


```json
{
  "Auth":
  {
    "SLACK_LOGGER_WEBHOOK": "<WEBHOOK_URL>",
    "SENTRY_DSN": "<https://ID@sentry.io/ID>"
  }
}
```

After the environment variables are setup in the _properties file_, one can run the deploy task for the concerning module.