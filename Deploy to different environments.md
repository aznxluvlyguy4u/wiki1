## Deploy to different environments

|                                                                              |
|------------------------------------------------------------------------------|
| 0. [Default environment](#markdown-header-default-environment)           |
| 1. [Mandatory steps for all environments](#markdown-header-mandatory-steps-for-all-environments)|
| 2. [Deploy to Dev](#markdown-header-deploy-to-dev)           |
| 3. [Deploy to Staging](#markdown-header-deploy-to-staging)     |
| 4. [Deploy to Production](#markdown-header-deploy-to-production)                             |

For now a manual change needs to be done to two files in order to deploy to different environments.
This will be fixed and automated, but for now it is a manual step.

We use the [Serverless framework](https://serverless.com) to deploy.

## Default environment

- The `serverless.yml` file found in every module is the default Serverless config file

- The `serverless.yml` is per **default** the _dev_ environment

## Mandatory steps for all environments

### 1 Exclude local dependencies from deployable archive

-  Uncomment the configurations block in the parent `build.gradle` file in the _root_ of the project, that looks something like this:

See the concerning _configuration_ block [here](https://bitbucket.org/oceanpremium/ocean-premium-api/src/0d0267dee6352416585faa3165a12f0fad583fe8/build.gradle#lines-233:241)

```
configurations {
  runtime.exclude module: "spring-boot-starter-web"
  ...
}
```

### 2 Set stageToDeployTo variable 

- Set in the [build.gradle](https://bitbucket.org/oceanpremium/ocean-premium-api/src/fbbe4dbaa85d3778586714bd3b734ff93711da05/build.gradle#lines-291:293), the variable [stageToDeployTo](https://bitbucket.org/oceanpremium/ocean-premium-api/src/fbbe4dbaa85d3778586714bd3b734ff93711da05/build.gradle#lines-291:293) to the concerning environment

- **Again**: dev is _default_ 
- staging 
- prod

### 3 Set the correct Serverless configuration file for the concerning environment

#### Deploy to Dev

For the _dev_ environment there has been setup a **default serverless config file**: `serverless.yml` in every module.

- Make sure to follow the [mandatory step](#markdown-header-mandatory-steps-for-all-environments) first, then proceed

- **Again**: the _dev_ environment is the _default_ deploy / Serverless stage environment, no additional configs needed

- Deploy:

```
$ ./gradlew <moduleName>:deploy -Pstage=dev --stacktrace -Pprofile=oceanpremium-serverless-publisher
```

- After succeeded deployment, see [after deployment instructions](#markdown-header-after-deployment)

#### Deploy to Staging

For the _staging_ environment there has been setup **a separate serverless config file**:
`serverless-template-staging.yml` in every module. 

- Rename the default `serverless.yml` to `serverless-template-dev.yml` 

- Rename the staging file: `serverless-template-staging.yml` to `serverless.yml`

- Then deploy:

```
 $ ./gradlew <moduleName>:deploy -Pstage=staging --stacktrace -Pprofile=oceanpremium-serverless-publisher
```

- After succeeded deployment, see [after deployment instructions](#markdown-header-after-deployment)

#### Deploy to Production

For the _production_ environment there has been setup **a separate serverless config file**: `serverless-template-production.yml` in every module.

- Rename the default `serverless.yml` to `serverless-template-dev.yml` 

- Rename the staging file: `serverless-template-production.yml` to `serverless.yml`

- Then deploy:

```
 $ ./gradlew <moduleName>:deploy -Pstage=prod --stacktrace -Pprofile=oceanpremium-serverless-publisher
```

- After succeeded deployment, see [after deployment instructions](#markdown-header-after-deployment)

##### After deployment

*Below instructions are only needed for _staging & production_ environment*

- Rename the file: `serverless.yml` back to: `serverless-template-<staging/production>.yml` 

- Rename the file: `serverless-template-dev.yml` back to `serverless.yml`

- Undo the changes / settings done in the [Mandatory steps for all environments](#markdown-header-mandatory-steps-for-all-environments).