## Creating AWS Step Functions using Serverless

This repo provides an example on creating AWS Step Functions using Serverless Framework.

### Prerequisites
- Set-Up and Configure AWS-CLI with access-key and secret-key. 
- Node/NPM is the prerequisite for installing serverless. The installation steps can be found here for [node-debian](https://tecadmin.net/install-latest-nodejs-npm-on-ubuntu/) and [node-centos](https://tecadmin.net/install-latest-nodejs-and-npm-on-centos/).
- Use the following command to install serverless.
```sh
$ npm -g insall serverless 
```
- As we are using serverless-plugins. Make sure these are installed.
```sh
$ sudo sls plugin install -n serverless-python-requirements
$ sudo sls plugin install -n serverless-step-functions
$ sudo sls plugin install -n serverless-pseudo-parameters 
```
- If the above commands give an exception, try this way.
```sh
$ sudo sls deploy <sls_plugin_name> -r <AWS_Region_Name> --stage <Stage_Name>
$ sudo sls plugin install -n serverless-pseudo-parameters  -r us-east-1 --stage test
```

### Usage

- Clone the repo and run the following command to spin-up infra in AWS.
```sh
$ sudo sls deploy -r <AWS_Region_Name> --stage <Stage_Name>
$ sudo sls deploy -r us-east-1 --stage test
```
- This command triggers serverless to create a AWS-CloudFormation Stack and spin-up the respective resources in AWS environment.
- In Our Case, the stack creates a State Machine, Lambda Functions, IAM Role for Lambda Function.
