# CI-CD pipeline using CodeCommit-Build-Deploy in AWS

---
![HLD](./HLD.PNG)
---
### TABLE OF CONTENTS
- Introduction
What is AWS CodeCommit?

* Step 1: Create an AWS CodeCommit repository.

  Write buildspec.yml file for code build & store artifacts in s3 Bucket.Add Script for installing & starting NGINX Webserver
* Write appspec.yml file for codedeploy
* What is AWS CodeBuild?
* Step 2: Create a CodeBuild project
* What is CodeDeploy?
* What is AWS CodePipeline?
* Benefits:
* Step 3: Create a CodeDeploy application and deployment group
* Step 4: Create a CodePipeline
---
## Prerequisite

* Before we begin with the Project, we need to make sure we have the following prerequisites installed And Configured:

- AWS Account with Administrator policy. You Can also give Specific permission to the user. Make sure you Generate HTTPS Git credentials for AWS CodeCommit for the user. This can be used to push code from a local source to a CodeCommit repository.

- You can do this by going to IAM \=> Users \=> Security credentials => HTTPS Git credentials for AWS CodeCommit => Generate credentials.
EC2 Instance ( AMI- Ubuntu, Type- t2.micro, Region: us-east-1 )

- You can Install CodeDeploy Agent by running the below script while creating an ec2 instance or after that. and these steps are for Ubuntu AMI.

``` Code-deploy agent Script
#!/bin/bash
sudo apt-get update
sudo apt-get install ruby
sudo apt-get install wget
cd /home/ubuntu
wget https://aws-codedeploy-ca-central-1.s3.ca-central-1.amazonaws.com/latest/install
chmod +x ./install
sudo ./install auto
```
- Check code-deploy agent status command.
```
sudo service codedeploy-agent status
```
- Start service & restart service command.
```
sudo service codedeploy-agent start

sudo service codedeploy-agent restart
```
