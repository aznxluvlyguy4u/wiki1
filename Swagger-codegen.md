# Installation

Swagger UI - JVT development: http://jvt-dev-swagger-ui.s3-website-eu-west-1.amazonaws.com

- [Linux](#markdown-header-linux)
- [MacOS](#markdown-header-macosx)

## Prerequisites

- [OpenJDK 8](http://openjdk.java.net)

## Linux

### Swagger-codegen bash script 

- Save the following bash script as _swagger-codegen.sh_:

```bash
#!/bin/bash

# save this script as: swagger-codegen.sh
# Run:
#
# $ chmod u+x ./swagger-codegen.sh 
#
# after creating file, to add run permissions to file
#
# Call script as follows to generate an 'openapi.json' specs file:
# 
# $ ./swagger-codegen.sh /path/to/input/swagger.yml /path/to/output/resources
#
# Now the openapi.json file in: '/path/to/resources/openapi.json' that is generated to validate if it is properly formed
#
SWAGGER_YML_INPUT_PATH=$1 # first argument passed
JSON_OUTPUT_PATH=$2 #second argument passed

java -jar /usr/local/bin/swagger-codegen-cli generate -i $SWAGGER_YML_INPUT_PATH -l openapi \
&& mv openapi.json $JSON_OUTPUT_PATH

echo "Done, generated specs file: $JSON_OUTPUT_PATH/openapi.json"

```

- Set executed permissions on script:

```shell
$ chmod u+x ./swagger-codegen.sh 
```

### Install Swagger-codegen-cli 3.0.4

Download binary and move it to /usr/local/bin:

Note *version 3.0.4* supports _openapi_ specs.

```shell
 $ wget http://central.maven.org/maven2/io/swagger/codegen/v3/swagger-codegen-cli/3.0.4/swagger-codegen-cli-3.0.4.jar -O /usr/local/bin/swagger-codegen-cli
```

### Generate openapi specs file

```shell
$ ./swagger-codegen.sh /path/to/input/swagger.yml /path/to/output/resources
```

#### Verify output file

```shell
$ cat /path/to/output/resources/openapi.json
```

Which will result in a generated _openapi.json_ file in the given output path which can be used for importing into [Postman](https://www.getpostman.com) and [Swagger UI](https://swagger.io/tools/swagger-ui/).

We at JVT already setup a Swagger UI that can be used for _development_: http://jvt-dev-swagger-ui.s3-website-eu-west-1.amazonaws.com

## MacOS

### Prerequisites

- [Brew](https://brew.sh/)

### Install swagger-codegen

```shell
$ brew install swagger-codegen  
```

### Generate openapi specs file

```shell
$ swagger-codegen generate -I /path/to/swagger.yml -l openapi
```
#### Verify output file

```shell
$ cat openapi.json
```

Which will result in a generated _openapi.json_ file in the given output path which can be used for importing into [Postman](https://www.getpostman.com) and [Swagger UI](https://swagger.io/tools/swagger-ui/).

We at JVT already setup a Swagger UI that can be used for _development_: http://jvt-dev-swagger-ui.s3-website-eu-west-1.amazonaws.com