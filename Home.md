# Ocean Premium - REST API

[![CircleCI](https://circleci.com/bb/oceanpremium/ocean-premium-api/tree/feature%2Fskeleton.svg?style=svg&circle-token=384a2a280e94bb67b80b424940eb58d7c41b1d69)](https://circleci.com/bb/oceanpremium/ocean-premium-api/tree/feature%2Fskeleton)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=alert_status)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=bugs)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=code_smells)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=coverage)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=vulnerabilities)

## Table of Content

| Table of Content                                                             |
|------------------------------------------------------------------------------|
| 0. [Setup & Configuration](#markdown-header-setup-&-configuration)           |
| 1. [Compile, build & run locally](#markdown-header-compile,-build-&-run)     |
| 2. [Local debugging](#markdown-header-debugging)                             |
| 3. [Deploying to cloud](#markdown-header-deploy)                             |
| 4. [Architecture](#markdown-header-architecture)                             |
| 5. [REST API documentation](#markdown-header-REST-API-documentation)         |
| 6. [Resources](#markdown-header-resources)                                   |

---
## Setup & Configuration

This sections describes on what the prerequisites are on getting started to get the application up and running.

### Prerequisites

#### OpenJDK 8
- [MacOS - adoptOpenJDK](https://adoptopenjdk.net)
- [Windows - OpenJDK](http://jdk.java.net/java-se-ri/8)
- [Linux - OpenJDK](http://openjdk.java.net/install/)

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

##### Swagger - API Doc

- [Swagger2OpenAPI](https://github.com/Mermade/oas-kit/blob/master/packages/swagger2openapi/README.md#swagger2openapi)

- [Swagger codegen](https://github.com/swagger-api/swagger-codegen)

## Setup & configurations

### Environment variables

TO BE DOCUMENTED

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
$ ./gradlew <module-name>:deploy
$ ./gradlew <module-name>:deploy --stacktrace
```

## Additional configurations / relevant information

TO BE DOCUMENTED

## Technical details

Like architectural design choices, algorithm explanations, ect

## Architecture

TO BE DOCUMENTED

## Dependencies

TO BE DOCUMENTED

## Resources

- [REST API Best practices](https://github.com/tfredrich/RestApiTutorial.com/raw/master/media/RESTful%20Best%20Practices-v1_2.pdf)

- [Ocean Premium - Jira Scrumboard](https://dudesoftechnology.atlassian.net/jira/software/projects/OP/boards/53)

- [Ocean Premium - Frontend]()

## Dependencies

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring AWS Lambda Container](https://github.com/awslabs/aws-serverless-java-container)
- [Hibernate - ORM](http://hibernate.org/orm/)
- [OKHttp - HTTP client](https://square.github.io/okhttp/)
- [Roboslack - Slack logger](https://github.com/palantir/roboslack)
- [Sentry - Error monitoring](https://docs.sentry.io/clients/java/)
- [SonarQube Gradle plugin](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Gradle)
