## Deploy to different environments

For now a manual change needs to be done to two files in order to deploy to different environments.
This will be fixed and automated, but for now it is a manuel step.


- Set the _stage_ to the environment in the `serverless.yml` file.

- Append the environment name to the function _definition and name_ in the `serverless.yml` file.

```yaml
# The provider of the cloud instance and its needed runtime configuration
provider:
  ...
  stage:  ${opt:stage, 'staging'}

# The service name which is used to create the stack
service:
  name: ocean-premium-products-api

...
functions:
  get-product-api-docs-<ENVIRONMENT>:
    # The function handler to be called for this endpoint
    handler: com.oceanpremium.api.products.Handler::handleRequest
    name: get-product-api-docs-<ENVIRONMENT>
    ...
```  

- Set _stageToDeploy to environment in `gradle.build` file in the _deploy task_

```groovy
task deploy(type: Exec) {
        ...
        def stageToDeployTo = "<ENVIRONMENT>"
        ...
```