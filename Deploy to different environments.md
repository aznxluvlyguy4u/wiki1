## Deploy to different environments


|                                                                              |
|------------------------------------------------------------------------------|
| 0. [Default environment](#markdown-header-default-environment)           |
| 1. [Mandatory steps for all environments](#markdown-header-mandatory-steps-for-all-environments)|
| 2. [Deploy to dev](#markdown-header-deploy-to-dev)           |
| 3. [Deploy to staging](#markdown-header-deploy-to-staging)     |
| 4. [Deploy to production](#markdown-header-deploy-to-production)                             |

For now a manual change needs to be done to two files in order to deploy to different environments.
This will be fixed and automated, but for now it is a manual step.

We use the [Serverless framework](https://serverless.com) to deploy.

## Default environment

- The `serverless.yml` file found in every module is the default Serverless config file

- The `serverless.yml` is per **default** the _dev_ environment

## Mandatory steps for all environments

### 1 Exclude local dependencies from deployable archive

-  Uncomment the configurations block in the parent build.gradle file in the root of the project, that looks something like this:

See the concerning _configuration_ block [here](https://bitbucket.org/oceanpremium/ocean-premium-api/src/0d0267dee6352416585faa3165a12f0fad583fe8/build.gradle#lines-233:241)

```
configurations {
  runtime.exclude module: "spring-boot-starter-web"
  ...
}
```

### 2 Set stageToDeployTo variable 

- Set in the [build.gradle](https://bitbucket.org/oceanpremium/ocean-premium-api/src/fbbe4dbaa85d3778586714bd3b734ff93711da05/build.gradle#lines-291:293), the variable `stageToDeployTo` to the concerning environment (dev (default) / staging / prod)

The variable is found in the `deploy` task definition, see [here](https://bitbucket.org/oceanpremium/ocean-premium-api/src/fbbe4dbaa85d3778586714bd3b734ff93711da05/build.gradle#lines-291:293)

### 3 Set the correct Serverless configuration file for the concerning environment

#### Dev

- No additional configs needed

The following instructions only apply to the _staging & prod_ environment.

#### Staging

For the _staging_ environment there has been setup **a separate serverless config file**:
`serverless-template-staging.yml` in every module. 

- Rename the default `serverless.yml` to `serverless-template-dev.yml` 

- Rename the staging file: `serverless-template-staging.yml` to `serverless.yml`

- Then deploy and see the [after deployment instructions](#markdown-header-after-deployment)

#### Production

- Rename the default `serverless.yml` to `serverless-template-dev.yml` 

- Rename the staging file: `serverless-template-production.yml` to `serverless.yml`

- Then deploy and see the [after deployment instructions](#markdown-header-after-deployment)

##### After deployment

- Rename the file: `serverless.yml` back to: `serverless-template-<staging/production>.yml` 

- Rename the file: `serverless-template-dev.yml` back to `serverless.yml`

- Set in the build.gradle, variable back to stageToDeployTo = "dev"

### Deploy to dev

- Make sure to follow the [mandatory step](#markdown-header-mandatory-steps-for-all-environments) first, then proceed

The _dev_ environment is the default deploy / Serverless stage environment. 

- Either deploy through gradle task:

```
 $ ./gradlew <moduleName>:deploy -Pstage=dev --stacktrace
```

  or directly via server-less (which is called by the `deploy` Gradle task):

```
$ sls deploy --region eu-west-1 --verbose --stage dev
```

### Deploy to Staging

- Make sure to follow the [mandatory step](#markdown-header-mandatory-steps-for-all-environments) first, then proceed

For the _staging_ environment there has been setup **a separate serverless config file**:
`serverless-template-staging.yml` in every module. 

- Either deploy through gradle task:

```
 $ ./gradlew <moduleName>:deploy -Pstage=staging --stacktrace
```

  or directly via server-less (which is called by the `deploy` Gradle task):

```
$ sls deploy --region eu-west-1 --verbose --stage staging
```

- Make sure to [revert settings and config files](#mark-down-header-after-deployment) back to default state

### Deploy to Production

- Make sure to follow the [mandatory step](#markdown-header-mandatory-steps-for-all-environments) first, then proceed

For the _production_ environment there has been setup **a separate serverless config file**:
`serverless-template-production.yml` in every module. 


- Either deploy through gradle task:

```
 $ ./gradlew <moduleName>:deploy -Pstage=prod --stacktrace
```

  or directly via server-less (which is called by the `deploy` Gradle task):

```
$ sls deploy --region eu-west-1 --verbose --stage prod
```

- Make sure to [revert settings and config files](#mark-down-header-after-deployment) back to default state