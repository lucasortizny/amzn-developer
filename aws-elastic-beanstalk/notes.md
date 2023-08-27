# AWS Elastic Beanstalk

### What is AWS Elastic Beanstalk?

Allows you to upload code of your web application along with environment configurations.

Automatically provision and deploy the appropriate and necessary resources required within AWS to make the web application
operational. 

These resources can include other AWS services and features and features, such as EC2, Auto Scaling, application health-monitoring
and Elastic Load Balancing in addition to capacity provisioning. 

This automation and simplification makes it an ideal service for engineers.

To DEPLOY the correct infrastructure to run the uploaded code. 

Continue to support the environment and maintain them. Very flexible service for the DevOps team.
Compatible with the following:
- Packer Builder
- Single Container Docker
- Multicontainer Docker
- Preconfigured Docker
- Go
- Java SE
- Java with Tomcat
- .NET on Windows Server with IIS
- Node.js
- PHP
- Python
- Ruby

Service itself is free to use. The resources created will be charged.

#### Application Version

Specific reference to deployable code. Typically point to S3.

#### Environment

Refers to Application Version deployed to AWS Resources. Deployed as a solution and becomes operational in your environment. 
Comprised of all the resources made by Elastic Beanstalk

#### Environment Configuration

Collection of settings dictate how an environment will have its resource provisioned by Elastic Beanstalk.

#### Environment Tier

This component reflects on how Elastic beanstalk provisions resources based on the application.  ]

#### Configuration Template

Template that provides baseline for creating new, unique, environment configuration. 

#### Platform

OS of the instance, the programming language, the server type (web or application) and components of Elastic Beanstalk itself.

#### Applications

An Application is a collection of different elements, such as environments, env configs, and application versions. 