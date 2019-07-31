# Run config setup

## Environment variables setup

Below instructions are needed to run every seperate Serverless Gradle Module (Products / Locations / Offices ect).

In Intellij create a run configuration:

- right-click on a function _Handler_, like for [example](https://bitbucket.org/oceanpremium/ocean-premium-api/src/571f963fdbe4566a78f2688dd1566ee912cd7680/auth/src/main/kotlin/com/oceanpremium/api/auth/Handler.kt):
_auth/src/main/kotlin/com/oceanpremium/api/auth/Handler.kt_

![Screenshot 2019-04-14 at 14.43.32.png](https://bitbucket.org/repo/qEd965M/images/3090632487-Screenshot%202019-04-14%20at%2014.43.32.png)

![Screenshot 2019-04-14 at 14.40.21.png](https://bitbucket.org/repo/qEd965M/images/1635358268-Screenshot%202019-04-14%20at%2014.40.21.png)

- Select `<ModuleName>Driver` -> _Run_, then _stop the run_


- Edit the _run configuration_

Click the environment variables and setup all the needed environment variables as instructed [here](https://bitbucket.org/oceanpremium/ocean-premium-api/wiki/Home#markdown-header-environment-variables)

![Screenshot 2019-04-14 at 14.40.41.png](https://bitbucket.org/repo/qEd965M/images/814402249-Screenshot%202019-04-14%20at%2014.40.41.png)

## JMX Agent

If during build & run you get the following error:

- `org.springframework.beans.factory.BeanCreationException: Error creating bean with name `
- `Caused by: javax.management.InstanceAlreadyExistsException:org.springframework.boot:type=Admin,name=SpringApplication`

Make sure you **DISABLE JMX agent** in config editor and re-run again:

![Disable.png](https://bitbucket.org/repo/qEd965M/images/147241789-Disable.png)