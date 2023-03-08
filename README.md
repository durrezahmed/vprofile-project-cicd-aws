# DevOps Project - Continuous Integration and Continuous Delivery of Vprofile Project on AWS Cloud

This is a DevOps project for [CI/CD](https://www.redhat.com/en/topics/devops/what-is-ci-cd) (Continuous Integration and Continuous Delivery) of vprofile project on [AWS Cloud](https://aws.amazon.com/) using [AWS CodeCommit](https://aws.amazon.com/codecommit/), [AWS CodeArtifact](https://aws.amazon.com/codeartifact/), [AWS CodeBuild](https://aws.amazon.com/codebuild/), [AWS Systems Manager Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html), [SonarCloud](https://www.sonarsource.com/products/sonarcloud/), [Amazon S3](https://aws.amazon.com/s3/), [AWS CodePipeline](https://aws.amazon.com/codepipeline/), [Amazon SNS](https://aws.amazon.com/sns/) etc. This project is a continuation of [_vprofile-project-ci-aws_](https://github.com/durrezahmed/vprofile-project-ci-aws) project.

[Link](https://github.com/durrezahmed/vprofile-project-devops) for vprofile app repository.

## Problem - Issues with Current Situation:

- In an Agile SDLC, there will be Frequent Code Changes

- Manual Code Deployment is Time Consuming

- Developer and Testers not equipped with Ops Knowledge

- Need to Hire Ops Professionals

- Or Outsource

- Dependency on Ops Team

- CI/CD Server Maintenance

- Operational Overhead to Maintain Servers like Jenkins, Nexus, Sonar, Git, QA Server for Testing

## Solution - Fix:

- PaaS (Platform as a Service) and SaaS (Software as a Service) Cloud Services

- Disposable Environment

- Automate Cl/CD Process

- Build, Test, Deploy and Test for Every Commit

## Benefits - CI/CD Pipeline on Cloud:

- Short MTTR (Mean Time to Recovery)

- No Human Intervention

- Fault Isolation

- Agile

- No Ops

## AWS Services and Tools used in the Project:

- [**AWS CodeCommit**](https://aws.amazon.com/codecommit/) - Version Control System

- [**AWS CodeArtifact**](https://aws.amazon.com/codeartifact/) - Maven Repository for Dependencies

- [**AWS CodeBuild**](https://aws.amazon.com/codebuild/) - Build Service from AWS

- [**AWS CodeDeploy**](https://aws.amazon.com/codedeploy/) - Artifact Deployment Service

- [**AWS CodePipeline**](https://aws.amazon.com/codepipeline/) - Service to Integrate all Jobs Together

- [**Amazon S3**](https://aws.amazon.com/s3/) - Artifact Deployment

- [**AWS Systems Manager Parameter Store**](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) - Hierarchical Parameters Storage

- [**SonarCloud**](https://www.sonarsource.com/products/sonarcloud/) - SonarQube Cloud based Tool

- [**Checkstyle**](https://checkstyle.org/) - Code Analysis from Build Job

- [**Selenium (Software Testing)**](https://www.selenium.dev/) - Code Build and Others

- [**AWS Elastic Beanstalk**](https://aws.amazon.com/elasticbeanstalk/) - For Hosting Application

- [**Amazon RDS**](https://aws.amazon.com/rds/) - Database for Application Service

- [**Amazon SNS**](https://aws.amazon.com/sns/) - Notification Service from AWS

## Comparison of Services:

| Services Used         | In Comparison Of   |
| --------------------- | ------------------ |
| `AWS CodeCommit`      | `GitHub`           |
| `AWS CodeArtifact`    | `Nexus Sonatype`   |
| `AWS CodeBuild`       | `Jenkins Jobs`     |
| `SonarCloud`          | `SonarQube Server` |
| `AWS CodePipeline`    | `Jenkins Pipeline` |
| `Beanstalk Instances` | `Tomcat VMs`       |
| `Amazon RDS`          | `MySQL VMs`        |

## Usage (Flow of Execution) - Cloud CICD Steps:

1. Login to AWS account - [Link](https://aws.amazon.com/marketplace/management/signin) to Login to your AWS Account.

2. AWS CodeCommit

   a. Create CodeCommit Repository

   b. Sync it with Local Repository

3. AWS CodeArtifact

   a. Create Repository

   b. Update `settings.xml` file in Source Code Top Level Directory

   c. Update `pom.xml` file with Repository Details

   d. Generate Token and Store in `SSM Parameter Store`

4. Sonar Setup

   a. Create Sonar Cloud account

   b. Generate Token and Store in `SSM Parameter Store`

   c. Create Build Project

   d. Update `CodeBuild` Role to access `SSM Parameter Store`

5. Create Notifications for SNS or Slack

6. Build Project

   a. Create Variables in `SSM Parameter Store`

   b. Create Build Project

7. Create Pipeline

   a. CodeCommit

   b. Test Code

   c. Build

   d. Deploy to S3 Bucket

8. Create Elastic Beanstalk and RDS

9. Update RDS Security Group

10. Deploy Database in RDS

11. Update `settings.xml` and `pom.xml` files

12. Create another Build Job to create artifact with buildspec file in repository

13. Create a Deploy Job to Elastic Beanstalk

14. Create a Build Job for Software Testing

15. Upload Screenshot to S3 Bucket

16. Update Pipeline

    a. CodeCommit

    b. Test Code

    c. Build and Store

    d. Deploy to S3 Bucket

    e. Build and Release

    f. Deploy to Elastic Beanstalk

    g. Build Job for Selenium Test Scripts

    h. Upload result to S3 Bucket

17. Test Pipeline
