# Introduction to the AWS Certified Developer Associated certification (DVA-C02)

## Target of the certification

This certification is intended for developers who have 1 or more years developing and mantaining an AWS based application. Validates the skills required to develop and optimize applications on AWS, package and deploy through CI/CD, secure application code and data and identify and resolve application issues.

One of the main documents to consult while preparing for this certificate is the _AWS Certified Developer Associate exam guide_, since it outlines the topics covered in the exam. This guide references 4 domains:

1. Development in AWS Services
  - Developing application for AWS
  - Developing code in AWS Lambda
  - Using data stores

The questions in this domain focus on understanding architectural patterns, and fault-tolerant design patterns, as well as the difference between stateful and stateless, tightly coupled and loosely coupled components, and synchronous and asycncrhonous patterns.

Most questions will relate to configuring and integrating Lambda functions. Using code to handle event lifecycle and errors, and writing and running tests code and continual optimization for optimal performance. Lastly, question related to managing and mantaining data stores, adding persistance to your data stores by serializing and deserializing the data, managing the data lifecycle, and integrating data caching services.

2. Security

 - Implementing authentication and authorization.
 - Encryption
 - Management of sensitive data.

Questions focus on understanding and securing applications based on bearer token authentication, federated access with identity providers, configuring programatic access, making authentication calls, and assuming IAM roles. A deeper dive into encryption keys, using ecryption across account boundaries, enabling and diabling key rotations and generating certificates.

This section is always a big part of the AWS certifications exams, to ensure you can encrypt environmental variables and use secret management services to secure sensitive data.

3. Deployment

 - Preparing and deploying application artifacts to AWS
 - Testing applications in development environments
 - Automating deployment testing
 - Deploying code using AWS CI/CD services

Questiong will relate to the management and optimization of your requirements, code, code repositories, and files or directories. Questions on how to resolve integration dependencies, perform mock integrations for APIs, use endpoints to test applications and how to deploy application stack updates.

We will dive deeper into deployment automation, and answering questions around application test events, deploying API resources, implementing infrastructure as code, and using CI/CD services, version controls, release, rollbacks, and runtime configurations.

4. Troubleshooting and optimization

 - Root cause analysis
 - Observability
 - Application optimization

 The questions will focus on identifying bugs in the code by interpreting metrics, logs, and traces. Also about querying logs and implementing custom metrics. Questions range from logging strategies with notification alerts, implementing tracing with AWS services and tools, adding annotations for tracing services.

 You will have to answer questions on how to use application requirements to determine the needed memory and the compute power, profile the application performance, cache content based on request headers, use subscription filter policites to optimize messagings.

## Services needed to kown in order of importance and frecuency of appearance in the tests

### Tier 1

Services you need to know

- Lambda
- API Gateway
- DynamoDB
- S3
- SQS & SNS
- IAM

They ALWAYS show up in the certification exam.

### Tier 2

Services you need to understand conceptually

- Cognito
- KMS
- Secret Manager & Parameter Store
- X-Ray
- CloudWatch
- CodePipeline
- CloudFormation & SAM
- EventBridge
- Step Functions
- ElasticCache

They usually show up but they do not require the same depth of knowledge as the Tier 1 services.

### In Between Tier 1 and 3

- Elastic BeanStore
- ECS

You need to understand the problems they show when you use them and basics on how they handle deployments

### Tier 3

Awareness Level

- Kinesis
- AppSYnc
- Amplify

## Plan 

### 1st Step: Diagnostic and gap analysis

Take a mock test to know your actual level and the gaps of the knowledge you are missing.

### 2nd Step: Core services deep dive.

- Deep on Lambda:
  - How does it triggered
  - How does it scale
  - How to handle errors
  - What is their runtime
  - How you can deploy them

- Deep on API Gateway
  - What are different types 
  - How do you control traffic
  - What are the authorization options

  Resolve 20-30 questions in this two services