
# The Task 

This repo contains CloudFormation code to deploy a VPC and ECS Fargate service to AWS.

## Scenario

A team has requested support to get their nginx container running on ECS Fargate with a public facing endpoint, and they plan to connect the app to the database and S3 bucket at a later stage.

Fix any issues and make improvements to the cloudformation templates relating to reliability, scalability, performance, observability and security.

## Tips

- We would like you spend no more than two hours on this task.
- If you run out of time, describe your intentions in the NOTES.md file.
- Plan your time before you start coding. Start small and add changes incrementally.
- We don't expect to see any changes to the container image.
- Be prepared to explain your decisions 

# Deployment

Deploying the stack is optional, if you would like to deploy the commands are:

## Deploy the vpc stack
```
aws cloudformation create-change-set --stack-name test-vpc --change-set-name vpc-change-set-1 --template-body file://./cloudformation/vpc/vpc.yaml --change-set-type CREATE

aws cloudformation describe-change-set --stack-name test-vpc --change-set-name vpc-change-set-1

aws cloudformation execute-change-set --stack-name test-vpc --change-set-name vpc-change-set-1
```
## Deploy the service stack
```
aws cloudformation create-change-set --stack-name test-service --change-set-name service-change-set-1 --template-body file://./cloudformation/service/service.yaml --capabilities CAPABILITY_IAM --change-set-type CREATE

aws cloudformation describe-change-set --stack-name test-service --change-set-name service-change-set-1

aws cloudformation execute-change-set --stack-name test-service --change-set-name service-change-set-1
```

# Submission

Clone or fork this project into a publicly accessible git repository of your own, and email the URL to to tpadberg@qmetric.co.uk.

Good Luck!
