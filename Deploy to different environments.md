## Deploy to different environments

For now a manual change needs to be done to two files in order to deploy to different environments.
This will be fixed and automated, but for now it is a manuel step.


### Dev (default)

The _dev_ environment is the default deploy / Serverless stage environment

In order to deploy to a the _dev_ environment for a given module, follow these steps:

-  Uncomment the configurations block in the parent build.gradle file in the root of the project, that looks something like this:

```
configurations {
  runtime.exclude module: "spring-boot-starter-web"
  ...
}
```

- Either deploy through gradle task:

```
 $ ./gradlew locations:deploy -Pstage=staging --stacktrace
```

  or directly via server-less (which is called by the `deploy` Gradle task):

```
$ sls deploy --region eu-west-1 --verbose --stage staging
```

### Staging

### Production