This page is intended to describe the various software engineering definitions and processes encounters during the development of the Ocean Premium Software. One should keep in mind that the terminology is used within the context of our Software Development Team and Software engineering field. 

## Index

[A](#markdown-header-a) [B](#markdown-header-b) [C](#markdown-header-c) [D](#markdown-header-d) [E](#markdown-header-e) [F](#markdown-header-f) [G](#markdown-header-g) [H](#markdown-header-h) [I](#markdown-header-i) [J](#markdown-header-j) [K](#markdown-header-k) [L](#markdown-header-l) [M](#markdown-header-m) [N](#markdown-header-n) [O](#markdown-header-o) [P](#markdown-header-p) [Q](#markdown-header-q) [R](#markdown-header-r) [S](#markdown-header-s) [T](#markdown-header-t) [U](#markdown-header-u) [V](#markdown-header-v) [W](#markdown-header-w) [X](#markdown-header-x) [Y](#markdown-header-y) [Z](#markdown-header-z)

### A

#### AWS

Website: [AWS](http://aws.amazon.com)

AWS is the platform we use for all cloud related things. It is where the frontend and backend are hosted.

### C

#### Continuous Integration (CI)

Continuous Integration (CI) is a software engineering practice in which frequent, isolated changes are immediately tested and reported on when they are added to a larger code base.

#### Continuous Deployment (CD)

Continuous Deployment (CD) aims to reduce the time elapsed between writing a line of code and making that code available to users in production.

#### CircleCI

Website: [circleci.com/](https://circleci.com/)

CircleCI is a tool we use to integrate CI and CD. Once we have programmed CircleCI correctly we can run test and deploy the application with one click of a button instead of running a lot of commands manually.

### G

#### Gradle

Website: [gradle.org](http://gradle.org)

Gradle is an advanced general purpose build management system based on Groovy and Kotlin. Gradle supports the automatic download and configuration of dependencies or other libraries.

### H

#### Hibernate

Website: [hibernate.org](https://hibernate.org)

Hibernate ORM (Hibernate in short) is an object-relational mapping tool for the Java programming language. It provides a framework for mapping an object-oriented domain model to a relational database. Hibernate handles object-relational impedance mismatch problems by replacing direct, persistent database accesses with high-level object handling functions.

### I

#### Integration testing

Integration testing is the phase in software testing in which individual software modules are combined and tested as a group. Integration testing is conducted to evaluate the compliance of a system or component with specified functional requirements.

### J

#### JSON Web Token (JWT)

Website: [jwt.io](https://jwt.io)

JSON web token is an industry standard way of providing access tokens. These access tokens contain information on what a user is allowed to see and what not. For example we don’t want User A to have insights into orders from User B. With JSON web tokens we make sure they don’t.

### P

#### Postman

Website: [getpostman.com](https://www.getpostman.com)

Postman is a tool used to test API endpoints, an example is an endpoint used to retrieve all the watertoys. In postman we can confirm that this endpoint actually returns all the water toys so that the frontend developer can implement it into the website

### R

#### Roboslack

Website: [github.com/palantir/roboslack](https://github.com/palantir/roboslack)

RoboSlack is a Java 8 API which handles all aspects of authenticating and sending messages to Slack as an incoming webhook service. This way you get a message to stay up to date on how users are using the platform at any time.

### S

#### SonarQube

Website: [sonarqube.org](https://www.sonarqube.org)

SonarQube is a tool we integrate into the CI process. This tool tests the code for any security issues. If it doesn’t pass the test the website will not be able to go live before this security issue is fixed.

#### Slack

Website: [slack.com](https://slack.com)

Slack is a tool we use to communicate with each other as a team. For this project we also get automated messages related to the project from tools like RoboSlack.

#### Swagger API

Website: [swagger.io](https://swagger.io)

Swagger gives insight into the structure on the backend and how to use it. It is mostly used for bridging the gap between frontend and backend developers.

#### Sentry

Website: [sentry.io](https://sentry.io)

Sentry is a tool similar like RoboSlack. But instead of events it will only log errors. These errors are sent to Slack so when anything goes wrong on the website. We know who it happend to and we have enough context to fix the issue.

### W

#### Wiki

In the wiki we write down any tasks that are hard to remember and need to be executed in order to use or work on the project. The wiki is written in a way that it is understandable for any developer.


Which has the following steps and goals:

A wiki with instructions will let any project member:

- get the application up and running on his/her computer

- has any addiontal steps documented on: how to configure the application,
  like: database setup / instructions on where to find credentials to connect to a database etc

The goal is to have knowledge shared (one source of truth), instead that one person knows everything and needs to (repeat)communication with multiple developers.

We currently maintain two wiki's for Ocean Premium:

- [Ocean Premium - API](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Home)
- [Ocean Premium - Front-end](https://bitbucket.org/jvt/ocean-premium-frontend/src)