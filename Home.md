# Ocean Premium - REST API

[![CircleCI](https://circleci.com/bb/oceanpremium/ocean-premium-api/tree/development.svg?style=svg&circle-token=384a2a280e94bb67b80b424940eb58d7c41b1d69)](https://circleci.com/bb/oceanpremium/ocean-premium-api/tree/development)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=alert_status)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=bugs)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=code_smells)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=coverage)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=vulnerabilities)

## Table of Content

|                                                                                                        |
|--------------------------------------------------------------------------------------------------------|
| 0. [Prerequisites](#markdown-header-prerequisites)                                                     |
| 1. [Setup & Configurations](#markdown-header-setup-and-configurations)                                 |
| 2. [Deployment](#markdown-header-deployment)                                                           |
| 2. [Additional configurations & relevant information](#markdown-header-additional-configurations-and-relevant-information)                   |
| 5. [Architecture](#markdown-header-architecture)                                                       |
| 6. [REST API documentation](API%20docs)                                                                |
| 7. [Resources](#markdown-header-resources)                                                             |
| 8. [Glossary with definitions](Glossary)                                                               |
| 9. [Current RMS](CurrentRMS)                                                                           |
| 10. [A to Z guide on how to import data exports](A-Z%20Guide%20to%20prepare%20CurrentRMS%20data%20for%20production)                                         |
| 11. [Hosting Provider](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Hosting%20provider)   | 
| 12. [Slack Logger - Search queries](#markdown-header-slack-logger-sales)

This sections describes on what the prerequisites are on getting started to get the application up and running.

### Prerequisites

#### OpenJDK 8
- [MacOS - adoptOpenJDK](https://adoptopenjdk.net)
- [Windows - OpenJDK](http://jdk.java.net/java-se-ri/8)
- [Linux - OpenJDK](http://openjdk.java.net/install/)

More info on available runtimes on AWS lambda, see [here](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html)

- [README (yes, do it, don't cheat, read it...) - Optimize cold starts and AVOID COMPONENT SCAN - CRUCIAL](https://github.com/awslabs/aws-serverless-java-container/wiki/Quick-start---Spring-Boot#optimizing-cold-start-times)

- [README yes, do it, don't cheat, read it... - Spring - Serverless - Cold start optimization - CRUCIAL](https://pattern-match.com/blog/2019/07/11/springboot2-and-aws-lambda-quick-fix/)

#### IDE

##### IntelliJ - IDEA - Ultimate

It is _strongly_ recommended (even mandatory) to use [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/)

- This codebase is written in [Kotlin](https://kotlinlang.org) and therefore the Kotlin language is tightly integrated into [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/)

- Kotlin is developed by the same people that produced [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/) ([JetBrains](https://www.jetbrains.com))

- Gradle: support is straight out of the box in [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/)

##### SonarLint - IntelliJ plugin

Because we use [SonarQube](http://sonarqube.org) for static code-analysis, we will also use the [SonarLint](https://www.sonarlint.org) plugin, which we are going to connect to our SonarQube Instance, to retrieve custom profiles for linting.

##### Credentials

- Ask Steven Gosseling / Frans Godschalk to share via Lastpass, for the following components:


###### CI
- [JVT CircleCI - Ocean Premium team access](https://circleci.com/bb/jvt/oceanpremium)

###### AWS
- [Ocean Premium AWS Console access](https://oceanpremium.signin.aws.amazon.com/console)
- [AWS CLI](https://github.com/aws/aws-cli)

###### Sentry.io - Error monitoring
- [Sentry.io](https://sentry.io)

###### Slack - JVT DevOps workspace
- [JVT Devops Workspace](https://jongensvantechniek.slack.com)

##### AWS CLI
Create an AWS profile (in: _~/.aws/credentials_) with the _profile name_: _oceanpremium-serverless-publisher_

*Note*: The credentials file is created by installing the [AWS CLI](https://github.com/aws/aws-cli) (thus installed it...)

##### Serverless plugin

- [Serverless NPM](https://serverless.com)

```shell
$ npm install serverless -g
```


## Setup and configurations

First make sure that the prerequisites are met, _then_ clone the repo:

```
$ git clone git@bitbucket.org:oceanpremium/ocean-premium-api.git
```

and switch to the development branch:

```
$ git checkout development
```

### Local run config

- See [here](Run%20config%20setup) on how to run locally

- See [Environment variables](#markdown-header-environment-variables) on how to setup environment variables for local run config

### Environment variables

There are two types of variables that need to be setup:

- **Local** environment variables via Intellij - for *local* running

- **Remote** environment variables via a _properties.json_ file, through Serverless framework - for *remote* running

Follow the following instructions for each module to setup (local & remote) environment variables:

- [Products module](Products%20Module%20-%20Environment%20variables)

- [Locations module](Locations%20Module%20-%20Environment%20variables)

- [Offices module](Offices%20Module%20-%20Environment%20variables)

- [Auth module **UNUSED**](Auth%20Module%20-%20Environment%20variables)

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

## Deployment

- Prerequisites - [Remote environment variables](#markdown-header-environment-variables)

### Deploy task

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


## Additional configurations and relevant information

### Categories / tags

- [Google excel sheet](https://docs.google.com/spreadsheets/d/1HRxENNZXQ5gENDhB0q0XaBUALOtMjPWXsyi_K1Pqn7U/edit?usp=sharing_eip&invite=COfnm-sF&ts=5daed89b)

### Transport cost

- [Transport cost - Flow diagram](https://teams.microsoft.com/_#/files/Ocean%20Premium?threadId=19%3Aed98c396e8644b90bc55479191ec0c28%40thread.skype&ctx=channel&context=transport%2520cost)

- [Transport cost - Excelt sheet](https://docs.google.com/spreadsheets/d/1rsm4a5N4jEDqoR_i1WsZkG4vFJMNGuZMEe7wDQutQ84/edit?usp=sharing)

### User signup (NOT USED)

- [Signup payload - current phase does not have this implementation](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Sign%20up%20endpoint%20payload%20formats)

See the branch [feature/demo-clean](https://bitbucket.org/oceanpremium/ocean-premium-api/branch/feature/demo_clean) for the sign up functionality.

**Again**: this current phase (phase 1) does not have this implementations, yet is was developed in Sprint 1, but not used!

### Slack Logger Sales

Invite link to a separate slack workspace, specifically created to log search queries:

https://join.slack.com/t/oceanpremiumsales/shared_invite/enQtODEzMTgzMTUwNTgyLTc1NDU1MDc4NjIzMzFkZTY2NzRiZWVkNTEyM2NiMTE4NTEzYzcyMjNiYjNmODRmYjE3YTgzY2QwNWYzNjQ1NWQ

Workspace url: https://oceanpremiumsales.slack.com


### [Swagger codegen](Swagger-codegen) (NOT USED)

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
- [How to interpret cold starts](https://hackernoon.com/im-afraid-you-re-thinking-about-aws-lambda-cold-starts-all-wrong-7d907f278a4f)
- [README - Spring - Serverless - Cold start optimization - CRUCIAL](https://pattern-match.com/blog/2019/07/11/springboot2-and-aws-lambda-quick-fix/)
- [README - Optimize cold starts and AVOID COMPONENT SCAN - CRUCIAL](https://github.com/awslabs/aws-serverless-java-container/wiki/Quick-start---Spring-Boot#optimizing-cold-start-times)