# Ocean Premium API

[![CircleCI](https://circleci.com/bb/oceanpremium/ocean-premium-api.svg?style=svg&circle-token=384a2a280e94bb67b80b424940eb58d7c41b1d69)](https://circleci.com/bb/oceanpremium/ocean-premium-api)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=alert_status) 
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=bugs)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=code_smells)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=coverage) 
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=vulnerabilities)

### Frontend repo

- [Frontend repo]()

## Project resources

- [SCRUM board]()
- [Documentation]()
- [Onedrive]()

## Repo guide

0. [Running locally](#markdown-header-running-locally)
0. [Debugging](#markdown-header-debugging)
0. [Deploying](#markdown-header-deploy)
0. [Request examples](Request%20examples)
0. [Architecture](#markdown-header-technical-details)
0. [Resources](#markdown-header-resources)

### Prerequisites

- [Serverless](https://github.com/serverless/serverless)
- [AWS CLI](https://github.com/aws/aws-cli)
- [Ocean Premium AWS Console access](https://oceanpremium.signin.aws.amazon.com/console)
- [JVT CircleCI access](https://circleci.com/bb/jvt/oceanpremium)
- [JVT Lastpass access](https://lastpass.com)
- [Java OpenJDK 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/)
- [Sonarlint](https://www.sonarlint.org)
- [Swagger2OpenAPI](https://github.com/Mermade/oas-kit/blob/master/packages/swagger2openapi/README.md#swagger2openapi)

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



## Dependencies

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring AWS Lambda Container](https://github.com/awslabs/aws-serverless-java-container)
- [Hibernate - ORM](http://hibernate.org/orm/)
- [OKHttp - HTTP client](https://square.github.io/okhttp/)
- [Roboslack - Slack logger](https://github.com/palantir/roboslack)
- [Sentry - Error monitoring](https://docs.sentry.io/clients/java/)
- [SonarQube Gradle plugin](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Gradle)