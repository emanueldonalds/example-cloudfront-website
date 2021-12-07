# Example static website with CloudFormation, CodePipeline and S3

This project contains a CloudFormation script that sets up a CloudFront distribution with SSL enabled in front of an S3 bucket. Continuous deployment is achieved with CodePipeline, with a GitHub repository as code source. 

# Setup
Either set the Default values of parameters in the CloudFormation script, or change the values in the UI when creating the stack.

## Origin Access Identity
An Origin Access Identity must exist. If you have none, create a new OAI in the CloudFront UI.

Set parameter ```CanonicalUser``` to the OAI Canonical user ID.

Set parameter ```OriginAccessIdentity``` to the OAI ID.

## SSL Certificate
Set parameter ```CertificateArn``` to the ARN of your desired certificate in ACM. Note that certificate must be in the us-east-1 region.

## DNS
Set parameter ```HostedZone``` to your hosted zone in Route53.

Set parameter ```DomainName```

## CodeStar source connection for GitHub.
A CodeStar source connection must be created manually for AWS to be able to retrieve source from GitHub. Create or use an existing connection.


Set parameter ```CodeStarConnectionArn``` to the ARN of the connection.

Set parameter ```GitHubRepo``` to your repository in GitHub.

## Create stack
Create a new stack in CloudFormation based on cloudformation.yml.
