# Ocean Premium API

[![CircleCI](https://circleci.com/bb/jvt/sheep-io-api.svg?style=svg&circle-token=8f290cdfedc362b063463dc2e116d2b9cd6c5416)](https://circleci.com/bb/jvt/ocean-premium-api)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=alert_status) 
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=bugs)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=code_smells)
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=coverage) 
![](https://sonar.jongensvantechniek.nl/api/project_badges/measure?project=com.oceanpremium.api&metric=vulnerabilities)

[**API DOC**](Request%20examples)

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

- [AWS CLI](https://aws.amazon.com/cli/)
- [AWS SAM Local CLI](AWS%20SAM%20Local)
- [Ocean Premium AWS Console access](https://jongensvantechniek.signin.aws.amazon.com/console)
- [JVT CircleCI access](https://circleci.com/bb/jvt/sheep-io-api)
- [JVT Lastpass access](https://lastpass.com)
- [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [Intellij IDEA - Ultimate](https://www.jetbrains.com/idea/)
- [Sonarlint](https://www.sonarlint.org)

## Setup & configurations

### Environment variables

With this [Gradle multi build project](https://guides.gradle.org/creating-multi-project-builds/) there is the notion of [modules](https://docs.gradle.org/current/userguide/multi_project_builds.html)

There are within the modules, two types:

- Core / non-serverless modules (which contain shared services / utils / models)

- Serverless modules (which contain Serverless functions / handlers)

We are going to setup _multiple_ `properties.json` files, namely _per module._

**Note 1**: a `properties.json` file should NOT be checked-in into version control, because it may contain credentials. It is therefore added to the `.gitgnore` file

**Note 2**: Every module should have a `properties.json.template` file (in the root of the module), which should already be structured to the needs of the concerning module

**Note 3**: the actual values for the `properties.json` file can be found on our [Lastpass](https://www.lastpass.com)

**Note 4**: See [here](Constructing%20properties%20template%20file) for more info on constructing a _properties.json.template_ file

#### Core module

The _Core_ module has a different configuration compared to the _serverless function modules_ concerning the placement location of the _properties.json_ file.

- Copy and paste the contents of `properties.json.template` file in a new file called: `properties.json` file in the *src/main/resources* directory of the **Core** module.

#### Serverless function modules

We are going to setup _multiple_ `properties.json` files, namely _per module._

- Copy and paste the contents of `properties.json.template` file in a new file called: `properties.json` file in the **root** of the concerning _serverless function_ module.


## Build & Run instructions

//TODO
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
Meaning: What (and how) does any tooling or the application needs to be configured to properly run

//TODO

## Technical details

Like architectural design choices, algorithm explanations, ect

## Architecture

//TODO

## Dependencies

meaning project dependencies and their source links (for example github repo link)

//TODO

## Resources

- [AWS SAM CLI](https://github.com/awslabs/aws-sam-cli)
- [REST API Best practices](https://github.com/tfredrich/RestApiTutorial.com/raw/master/media/RESTful%20Best%20Practices-v1_2.pdf)
- [SonarQube Gradle plugin](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Gradle)