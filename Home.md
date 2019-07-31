# Ocean Premium - REST API

[![CircleCI](https://circleci.com/bb/oceanpremium/ocean-premium-api/tree/feature%2Fskeleton.svg?style=svg&circle-token=384a2a280e94bb67b80b424940eb58d7c41b1d69)](https://circleci.com/bb/oceanpremium/ocean-premium-api/tree/feature%2Fskeleton)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=alert_status)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=bugs)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=code_smells)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=coverage)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=vulnerabilities)

## Table of Content

|                                                                              |
|------------------------------------------------------------------------------|
| 0. [Environments](#markdown-header-environments)                             |
| 1. [Setup & Configuration](#markdown-header-setup-&-configuration)           |
| 2. [Compile, build & run locally](#markdown-header-compile,-build-&-run)     |
| 3. [Local debugging](#markdown-header-debugging)                             |
| 4. [Deploying to cloud](#markdown-header-deploy)                             |
| 5. [Architecture](#markdown-header-architecture)                             |
| 6. [REST API documentation](API%20docs)                                      |
| 7. [Resources](#markdown-header-resources)                                                          |
| 8. [Glossary with definitions](Glossary)                                                            |
| 9. [Current RMS](CurrentRMS)                                                                        |
| 10. [A to Z guide](A-Z%20Guide%20to%20prepare%20CurrentRMS%20data%20for%20production)                |
| 11. [Hosting Provider](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Hosting%20provider) | 

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

## Setup & Configuration

This sections describes on what the prerequisites are on getting started to get the application up and running.

### Prerequisites

#### OpenJDK 8
- [MacOS - adoptOpenJDK](https://adoptopenjdk.net)
- [Windows - OpenJDK](http://jdk.java.net/java-se-ri/8)
- [Linux - OpenJDK](http://openjdk.java.net/install/)

More info on available runtimes on AWS lambda, see [here](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html)

#### IDE

##### IntelliJ - IDEA - Ultimate

It is _strongly_ recommended (even mandatory) to use [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/)

- This codebase is written in [Kotlin](https://kotlinlang.org) and therefore the Kotlin language is tightly integrated into [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/)

- Kotlin is developed by the same people that produced [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/) ([JetBrains](https://www.jetbrains.com))

- Gradle: support is straight out of the box in [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/)

##### SonarLint - IntelliJ plugin

Because we use [SonarQube](http://sonarqube.org) for static code-analysis, we will also use the [SonarLint](https://www.sonarlint.org) plugin, which we are going to connect to our SonarQube Instance, to retrieve custom profiles for linting.

##### Credentials

- Ask Steve / Yubin to share via Lastpass

##### CI
- [JVT CircleCI - Ocean Premium team access](https://circleci.com/bb/jvt/oceanpremium)

##### AWS
- [Ocean Premium AWS Console access](https://oceanpremium.signin.aws.amazon.com/console)
- [AWS CLI](https://github.com/aws/aws-cli)

Create an AWS profile (in: _~/.aws/credentials_) with the _profile name_: _oceanpremium-serverless-publisher_

*Note*: The credentials file is created by installing the [AWS CLI](https://github.com/aws/aws-cli) (thus installed it...)

##### Serverless plugin

- [Serverless NPM](https://serverless.com)

```shell
$ npm install serverless -g
```


## Setup & configurations

First make sure that the prerequisites are met, _then_ clone the repo:

```
$ git clone git@bitbucket.org:oceanpremium/ocean-premium-api.git
```

and switch to the development branch:

```
$ git checkout development
```

### Environment variables

#### Locally 

See [here](Run%20config%20setup) for setting up a Run configuration with environment variables in IntelliJ

### Products / Locations / Offices modules

- Input environment variables in _Environment Variables_ field

```
SENTRY_DSN=https://id@sentry.io/id
slack_webhook_jvt=https://hooks.slack.com/services/id
slack_webhook_op=https://hooks.slack.com/services/id
current_rms_token=api-token
current_rms_subdomain=oceanpremium-staging
current_rms_api_url=https://api.current-rms.com/api/v1/
emailer_smtp_host=smtp.office365.com
emailer_port=587
emailer_username=info@example.com
emailer_password=password
emailer_sender=info@example.com
emailer_back_office=info@example.com
env=dev
```

*NOTE: the SENTRY_DSN needs to be capitalised, in order to be picked up by the Sentry SDK*

See [LastPass](https://lastpass.com) for the values.

After the environment variables are setup, one can run the concerning run configuration to local run the API.

#### Remote

In order to pass environment variables to remote on a deploy task we utilise a _properties.json_ file.

The properties file *should not* be checked in to version control as it contains credentials. It is 
therefore added to the _.gitignore_.

- Make sure the [Serverless NPM package](https://serverless.com) is installed

- Create a `properties.json` file containing environment variables in the `root` of any (serverless) function module (thus not in _core_ module) of the following structure:

#### Products & Offices modules

```json
{
  "products": (or offices) <----------- SET THE CORRECT VERSION
  {
    "slack": {
      "webhook_jvt": "https://hooks.slack.com/services/id",
      "webhook_op": "https://hooks.slack.com/services/id"
    },
    "current_rms": {
      "token": "token value",
      "subdomain": "oceanpremium-staging",
      "api_url": "https://api.current-rms.com/api/v1/"
    },
    "emailer": {
      "smtp_host": "email-smtp.eu-west-1.amazonaws.com",
      "username" : "ses username",
      "password": "ses password",
      "sender": "<your-name>@jongensvantechniek.nl",
      "back_office": "<your-name>@jongensvantechniek.nl"
    },
    "sentry_dsn": "https://id@sentry.io/id",
    "env": "prod"
  }
}

```

#### Locations module

```json
{
  "locations":
  {
    "slack": {
      "webhook_jvt": "https://hooks.slack.com/services/id"
    },
    "current_rms": {
      "token": "token value",
      "subdomain": "oceanpremium-staging",
      "api_url": "https://api.current-rms.com/api/v1/"
    },
    "sentry_dsn": "https://id@sentry.io/id",
    "env": "prod"
  }
}
```

- *NOTE 1:* that the _rootNode_ name is the module name. 

- *NOTE 2: the sentry_dsn does not need to be capitalised in the `properties.json` file, **but** it does when defining it as a system environment variable*

See [lastpass](https://lastpass.com) for the credentials to be filled in.

### Logging

In the *<module-name>*_/src/main/kotlin/resources_ directory, create a _application.properties_ file with the following contents:

#### DEV 

```
logging.level.com.oceanpremium.api=DEBUG
```

#### PROD

```
logging.level.com.oceanpremium.api=INFO
```

For different log levels, see [here](https://stackoverflow.com/questions/7839565/logging-levels-logback-rule-of-thumb-to-assign-log-levels)


##### Swagger - API Doc

- [Swagger codegen](Swagger-codegen)

### Deploy

The **default** environment is: _dev_

To deploy to _different environments (other then `dev`, i.e.: `staging` or `production`)_, see [these](Deploy%20to%20different%20environments) instructions.

Currently to be able to deploy to _dev_ you have to _manually exclude_ dependencies from the build config. To do so, uncomment [the following lines in the build.gradle file](https://bitbucket.org/oceanpremium/ocean-premium-api/src/f6992542d4beaef9272642e6e525ab64e656f2d3/build.gradle#lines-197:205), **before** running the below deploy command. After you are done deploying, *undo* the uncommenting.

Currently a Serverless function module has the following Gradle tasks:

- deploy

```shell
$ ./gradlew <moduleName>:deploy -Pstage=dev -Pprofile=oceanpremium-serverless-publisher
```

- -Pstage: _to which environment the function needs to be deployed_

- -Pprofile: _which AWS credentials profile needs to be used to deploy, this determines to which AWS account is deployed, if multiple AWS account profiles are registered in the AWS CLI_


## Additional configurations / relevant information

- [Signup payload - current phase does not have this implementation](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Sign%20up%20endpoint%20payload%20formats)

See the branch [feature/demo-clean](https://bitbucket.org/oceanpremium/ocean-premium-api/branch/feature/demo_clean) for the sign up functionality.

**Again**: this current phase (phase 1) does not have this implementations, yet is was developed in Sprint 1, but not used!

## Architecture

![ocean_premium_architecture_1.0.png](https://bitbucket.org/repo/qEd965M/images/1016809427-ocean_premium_architecture_1.0.png)

[draw.io architecture file](Draw.io%20-%20Architecture%20diagram%20file)

## Resources

- [REST API Best practices](https://github.com/tfredrich/RestApiTutorial.com/raw/master/media/RESTful%20Best%20Practices-v1_2.pdf)

- [Ocean Premium - Jira Scrumboard](https://dudesoftechnology.atlassian.net/jira/software/projects/OP/boards/53)

- [Ocean Premium - Frontend](https://bitbucket.org/jvt/ocean-premium-frontend/wiki)

## Dependencies

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring AWS Lambda Container](https://github.com/awslabs/aws-serverless-java-container)
- [Hibernate - ORM](http://hibernate.org/orm/)
- [OKHttp - HTTP client](https://square.github.io/okhttp/)
- [Roboslack - Slack logger](https://github.com/palantir/roboslack)
- [Sentry - Error monitoring](https://docs.sentry.io/clients/java/)
- [SonarQube Gradle plugin](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Gradle)