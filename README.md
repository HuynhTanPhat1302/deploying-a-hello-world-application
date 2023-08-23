
# Deploying a hello world app with AWS SAM

[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

Using AWS Sam for Deploying a hello-world application. In this repository, you will find the instructions for Deploying the application to AWS Sam. Notes that the step-by-step instructions are in the Documentation which I gave below.

This repository contains:
- The sam-app (hello-world app)
- Documentation 



## Table of Contents

- [Installation](#Installation)
- [Documentaion](#Documentation)

## Installation

Prerequisite:
- Aws account
- Docker on local machine
- AWS & SAM CLI

Step 1: Install hello-world application

```sh
  sam init
```
Fill the parameters with the following:

- Template: 1
- Use the most popular runtime and package type? (Python and zip) [y/N]: y
- Would you like to enable X-Ray tracing on the function(s) in your application?  [y/N]: 
- Would you like to enable monitoring using CloudWatch Application Insights?
- For more info, please view https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch-application-insights.html [y/N]: 
- Project name [sam-app]:	

Step 2: Build the application

```sh
  sam build --use-container
```

Step 3: Deploy your application to cloud

```sh
  sam deploy –guided
```
Fill the parameters with the following:
- Stack Name [sam-app]:
- AWS Region [us-west-2]:
- Confirm changes before deploy [Y/n]: n
- Allow SAM CLI IAM role creation [Y/n]: 
- Disable rollback [y/N]: 
- HelloWorldFunction may not have authorization defined, Is this okay? [y/N]: y
- Save arguments to configuration file [Y/n]: 
- SAM configuration file [samconfig.toml]:
- SAM configuration environment [default]:

Step 4: Run your application

```sh
  sam list endpoints –output json
  curl https://api-link
```

Step 5: Interact with your function in the AWS cloud

```sh
  sam remote invoke HelloWorldFunction --stack-name sam-app
```

Step 6: Modify and sync your application code to the AWS Cloud

```sh
  sam sync –watch –use-container
```

Then modify your local code and check the api again.

Step 7: Test your application locally

```sh
  sam local invoke
```

Step 8: Delete your application from AWS Cloud

```sh
  sam delete
```

## Documentation

[Documentation](https://docs.google.com/document/d/1Zi8242uL4OkugsicrJbrR8zxIM4SBIGuEWeQiMq9C2M/edit?usp=sharing)


## Authors

[@HuynhTanPhat1302](https://www.github.com/HuynhTanPhat1302)


## License

[MIT](https://choosealicense.com/licenses/mit/) © HuynhTanPhat

