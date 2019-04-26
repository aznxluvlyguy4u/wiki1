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
| 0. [Setup & Configuration](#markdown-header-setup-&-configuration)           |
| 1. [Compile, build & run locally](#markdown-header-compile,-build-&-run)     |
| 2. [Local debugging](#markdown-header-debugging)                             |
| 3. [Deploying to cloud](#markdown-header-deploy)                             |
| 4. [Architecture](#markdown-header-architecture)                             |
| 5. [REST API documentation](API%20docs)                                      |
| 6. [Resources](#markdown-header-resources)                                   |
| 7. [Glossary with definitions](Glossary)                                     |
| 8. [Current RMS](CurrentRMS)

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

- Ask Steve

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

##### Swagger - API Doc

- [Swagger codegen](Swagger-codegen)

## Setup & configurations

### Environment variables

#### Local 

In Intellij create a run configuration:

- right-click on a function _Handler_, like for [example](https://bitbucket.org/oceanpremium/ocean-premium-api/src/571f963fdbe4566a78f2688dd1566ee912cd7680/auth/src/main/kotlin/com/oceanpremium/api/auth/Handler.kt):
_auth/src/main/kotlin/com/oceanpremium/api/auth/Handler.kt_

![Screenshot 2019-04-14 at 14.43.32.png](https://bitbucket.org/repo/qEd965M/images/3090632487-Screenshot%202019-04-14%20at%2014.43.32.png)

![Screenshot 2019-04-14 at 14.40.21.png](https://bitbucket.org/repo/qEd965M/images/1635358268-Screenshot%202019-04-14%20at%2014.40.21.png)

- Select `<ModuleName>Driver` -> _Run_


- Edit the _run configuration_

![Screenshot 2019-04-14 at 14.40.41.png](https://bitbucket.org/repo/qEd965M/images/814402249-Screenshot%202019-04-14%20at%2014.40.41.png)

- Input environment variables in _Environment Variables_ field

```
DATABASE_HOST=<host-id.example.com>
DATABASE_NAME=<DBNAME>
DATABASE_USER=<USERNAME>
DATABASE_PASSWORD=<PASSWORD>
```

#### Remote

In order to pass environment variables to remote on a deploy task we utilise a _properties.json_ file.

The properties file *should not* be checked in to version control as it contains credentials. It is 
therefore added to the _.gitignore_.

- Make sure the [Serverless NPM package](https://serverless.com) is installed

- Create a `properties.json` file containing environment variables in the `root` of any (serverless) function module (thus not in _core_ module) of the following structure:

```json
{
  "Module-name":
  {
    "SENTRY_DSN": "https://id@sentry.io/111111",
    "SLACK_LOGGER_WEBHOOK": "https://hooks.slack.com/services/ids",
    "DATABASE_HOST" : "id.eu-west-1.rds.amazonaws.com",
    "DATABASE_NAME" : "database-name",
    "DATABASE_USER" : "database-user",
    "DATABASE_PASSWORD": "database-password"
  }
}
```

*Note:* that the _rootNode_ name is the module name. 

See [lastpass](https://lastpass.com) for the credentials to be filled in.


#### Core module

TO BE DOCUMENTED

#### Serverless function modules

TO BE DOCUMENTED

## Build & Run instructions

TO BE DOCUMENTED

### Task

In the below example, replace `<module-name>` with the actual Gradle module name, for example:

```shell
$ ./gradlew <module-name>:someTask
```

if a **module** name is: `auth`, and a **task** is called: `build`, a command becomes:

```shell
$ ./gradlew auth:build
```

### Tasks per module

To see all available Gradle tasks, from root of project, run:

```shell
$ ./gradlew tasks --all
```

To see per module the available Gradle tasks, from root of project run:

```shell
$ ./gradlew <module-name> tasks --all
```

Have a look at the _Ocean Premium_ section to see our custom defined Gradle tasks.

```shell
$ ./gradlew tasks --all
```

Currently a Serverless function module has the following Gradle tasks:

- deploy

### Deploy

```shell
$ ./gradlew <moduleName>:deploy -Pstage=test|dev|stage|prod -Pprofile=oceanpremium-serverless-publisher
```

- -Pstage: _to which environment the function needs to be deployed_

- -Pprofile: _which AWS credentials profile needs to be used to deploy, this determines to which AWS account is deployed, if multiple AWS account profiles are registered in the AWS CLI_

## Additional configurations / relevant information

- [Signup payload](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Sign%20up%20endpoint%20payload%20formats)

## Technical details

Like architectural design choices, algorithm explanations, ect

## Architecture

![ocean_premium_architecture_1.0.png](https://bitbucket.org/repo/qEd965M/images/1016809427-ocean_premium_architecture_1.0.png)

[draw.io architecture file](Draw.io%20-%20Architecture%20diagram%20file)

## Dependencies

TO BE DOCUMENTED

## Resources

- [REST API Best practices](https://github.com/tfredrich/RestApiTutorial.com/raw/master/media/RESTful%20Best%20Practices-v1_2.pdf)

- [Ocean Premium - Jira Scrumboard](https://dudesoftechnology.atlassian.net/jira/software/projects/OP/boards/53)

- [Ocean Premium - Frontend](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/)

## Dependencies

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring AWS Lambda Container](https://github.com/awslabs/aws-serverless-java-container)
- [Hibernate - ORM](http://hibernate.org/orm/)
- [OKHttp - HTTP client](https://square.github.io/okhttp/)
- [Roboslack - Slack logger](https://github.com/palantir/roboslack)
- [Sentry - Error monitoring](https://docs.sentry.io/clients/java/)
- [SonarQube Gradle plugin](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Gradle)