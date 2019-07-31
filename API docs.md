# API docs

## Swagger UI

Ocean premium hosts it's own Swagger UI that can be used to see the API documentation for the *Ocean Premium - REST API:*

http://oceanpremium-swagger-ui.s3-website-eu-west-1.amazonaws.com

The Swagger specs _for each endpoint_ can be found on: _https://api-endpoint/api/v1/docs_

## Postman collection

The following collection contains both request examples to the *Ocean Premium* - REST API and the [CurrentRMS - REST API](https://api.current-rms.com/doc)

- [HTTP request collection](https://shopix99-my.sharepoint.com/:u:/g/personal/peter_jongensvantechniek_nl/EUUIHQjXJ75MifLkTotyb2kBToveIKQjOfE_Eofe1PfV3A?e=ENmCqU)

## Postman environment 

- [Postman environment variables](https://shopix99-my.sharepoint.com/:u:/g/personal/peter_jongensvantechniek_nl/ET9YnZ7wmPlAsFIU5BUt71oBR6Bc6M_V3oDHDh025uLwyQ?e=AxPoT6)

## Response codes overview

- `200`: OK (on only _GET_ endpoints)
- `201`: Created (on only _POST_ endpoints)
- `400`: Bad Request (on all _GET_ & _POST_ endpoints)
- `401`: Unauthorized (on all endpoints - *Currently only occurs if current RMS token is not valid or current RMS account associated with token is closed (trial account ended)*)
- `404`: Not Found (on all _GET_ & _POST_ endpoints)
- `429`: Too Many Requests (on all _GET_ & _POST_ endpoints)
- `500`: Server Error (on all _GET_ & _POST_ endpoints)

Class that builds the response codes:

https://bitbucket.org/oceanpremium/ocean-premium-api/src/development/core/src/main/kotlin/com/oceanpremium/api/core/exception/handler/GlobalExceptionHandler.kt

## Environments


## Products endpoint


|Env         | Base URL                                                                       |
|------------|--------------------------------------------------------------------------------|
|PRODUCTION  | https://y9gnyonusf.execute-api.eu-west-1.amazonaws.com/prod/api/v1/products    |
|STAGING     | https://zu6wjlgc49.execute-api.eu-west-1.amazonaws.com/staging/api/v1/products |
|DEVELOPMENT | https://1qie0vagy1.execute-api.eu-west-1.amazonaws.com/dev/api/v1/products     |

## Locations endpoint

|Env         | Base URL                                                                           |
|------------|------------------------------------------------------------------------------------|
|PRODUCTION  | https://p4is2qdxnd.execute-api.eu-west-1.amazonaws.com/prod/api/v1/locations       |
|STAGING     | https://7s2c5akwy2.execute-api.eu-west-1.amazonaws.com/staging/api/v1/locations    |
|DEVELOPMENT | https://3rk3xtficb.execute-api.eu-west-1.amazonaws.com/dev/api/v1/locations        |

## Offices endpoint

|Env         | Base URL                                                                           |
|------------|------------------------------------------------------------------------------------|
|PRODUCTION  | https://ig0smst338.execute-api.eu-west-1.amazonaws.com/prod/api/v1/offices         |
|STAGING     | https://856c4yiakc.execute-api.eu-west-1.amazonaws.com/staging/api/v1/offices      |
|DEVELOPMENT | https://s7cnld7i7c.execute-api.eu-west-1.amazonaws.com/dev/api/v1/offices          |