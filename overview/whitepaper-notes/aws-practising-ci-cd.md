# Practising Continuous Integration and Continuous Delivery

## The challenge of software delivery

Companies today face a rapidly changing competitive landscape, evolving security requirements. CI/CD are practises that enable rapid software changes while maintaining system stability and security.

This needs are needs also for Amazon.com, and its subsidiares have needed. Thousands of independent software teams must be able to work in parallel to deliver software quickly, securely and reliably.

This need is what made Amazon and other companies pioneers DevOps. DevOps is a combination of cultural philosophis, practices, and tools that increase an organizations ability to deliver applications and services at high velocity.

Some of these principles (two-pizza teams, microservices, service-oriented architecture or SOA) are out of the scope of this document. This paper focuses on the CI/CD capability that AWS provides.

AWS offers CI/CD capabilities as a set of developer services, such as Amazon CodeCatalyst and CodePipeline. They offer fast, safe and reliable software delivery. Combine the offer storage and version control of your application's source code.

CodeCatalys is a fully managed, unified software development service that makes it faster to build and deliver software.
CodePipeline has the flexibility to integrate each service independently of your existing tools, and that can be used on an already existing environment.

Both of these services can be accessed through AWS Management Console, AWS APIs and AWS software development toolkits (SDKs).

## Continuous Integration

Is a software development practice where developers regularly merge their code changes to a central repository, after which automated builds and tests are run. CI most often refers to the build or integration stage of the software release process and reuqire both an automation component (A CI or build service) and a cultural component (like learning to integrate frecuently). The key goals of CI are to find and address bugs more quickly, improve software quality, and reduce the time it takes to validate and release new software updates.

CI focuses on smaller commits and smaller code changes to integrate. A developer commits code at regular intervals, at minimum once a day. The developer pulls code from the code repository to ensure the code on the local host is merged before pushing to the build server. At this stage, the build server runs various tests abd eutger accepts or rejects the code commit.

It takes time to automate builds, as well as testing of projects into a full continuous integration process. Some of the challenges come from the increased frequency of commits, which increases the maintenance burden on the single source code repository, and increases hardware requirements to accommodate the testing of every change. Additional challenges include the creation of testing environments, that represent production without inclusion of sensitive data, providing visibility of the testing process to the team, and providing easy access to any version of the application.

## Continuous delivery and deployment

Continuous delivery (CD) is a software development practice where code changes are automatically built, tested, and prepared for production release. It expands on continuous integration by deploying all code changes to a testing environment, a production environment, or both after the build stage has been completed. 

It can be fully automated with a workflow process or partially automated with manual steps at critical points. When continuous delivery is properly implemented, developers always have a deployment-ready build artifact that has passed through a standarized test process.

With continuous deployment, revisions are deployed to a production environment automatically without explicit approval from a developer, making the entire software release process automated. This alllows for a continuous customer feedback loop early in the product lifecycle. 

## Continuous delivery is not continuous deployment

This is a common misconception. That continuous delivery means that every small commit is applied to production inmediately. However, the point of continuous delivery is not to apply every change to production, but to ensure that every change is production-ready.

Before we deploy a change in production we can implement a decision process to ensure that it is authorized and audited. This decision can be made by a person and then run by the tooling.

When using continuous delivery, the decision to go live becomes a bussines decision, not a technical one. The technical validation happends on every commit.

Rolling out a change to production is not a disruptive event. It does not require the team to stop working on the next set of changes, and it doesn't neead a project plan, maintenance window or a handover documentation. It becomes a repeatable process that has been carried out and proven multiple times in testing environment.

## Benefits of continuous delivery

CD gives out numerous benefits to the software development team, including automating the process, improving developer productivity, improving code quality, and fast delivery to the users.

### Automation of the software process

CD provides methods for the team to check in code code that is automatically built, tested and prepared for release to production so that your software delivery is efficient, resilient, rapid and secure.

### Improvement of developer productivity

CD practives will help your team's productivity by freeing developers from manual tasks, untangling complex dependencies, and returning focus on delivering new features in software. Instead of integrating their code with other parts of the bussiness, they can focus on coding.

### Improve code quality

CD helps you discover and address bugs early in the delivery process before they grow into large problems later. Your team can easily perform additional types of code test, because the entire process has been automated. With the discipline of more testing more frequently, teams can achieve high quality code with a high assurance of stability and security, Developers will know through immediate feedback whether the new code works and if any breaking changes or bugs are have been introduced.

### Deliver updates fast

When CI/CD is implemented, the velocity of the entire team, including the release of features and bug fixes, is increased. Entreprises can respond fasted to market changes, security challenges, customer needs and cost pressures. What use to take weeks and months can now be done in days or hours.

## Implementing continuous integration and continuous delivery

This section discusses the ways in which you can begin to implement a CI/CD model. It is not how a mature DevOps builds and uses a CI/CD pipeline.

### A pathway to CI/CD 

CI/CD can be pictured as a workflow or pipeline where new code is submitted to one end, tested over a series of stages (source, build, staging, production), and then pusblished as production-ready code. If your organization is new to CI/CD it can approach this pipeline in an iterative fashion, starting small, and iterating at each stage so that you can understand and develop your code in a way that will help your organization grow.

Each step of the CI/CD pipeline is a logical unit in the delivery process. Each step also acts as a gate that vets a certain aspect of the code. As the code progresses through the pipeline, the assumption is that the quality of the code is higher in the latter stages because more aspects of it had been verified. Problems uncovered in an early stage stop the code from progressing through. Results from the test are immediately sent to the team, and all further builds and releases are stopped.

The stages presented are sugestions. You can adapt them based on your business needs. Some stages can be repeated for multiple types of testing, security and performance.

The presence of a CI/CD pipeline will have a large impact on maturing the capabilities of your organization. The organization should start with small steps and not try to build a fully mature pipeline.

Building a CI/CD-enabled organization is a journey, and there are many destinations along the way. On the next section we will discuss a possible pathway to begin the journey.

#### CI - Source and build

The first phase is to develop maturity in CI. You should make sure that all developers regularly commit ther conde to a central repository and merge all changes to a release branch for the application. No developer should ne holding code in isolation. If a feature branch is needed for a certain period of time, it should be kept up to date bi merging from the upstream as often as possible. Frequent commits and merge with complete units of work are recommended for the team to develop discipline and are encouraged by the process.

You should encourage developers to create unit tests as early as possible for their applications, and to run these tests before pushing the code to the central repository. Errors caught early in the software development process are the cheapest and easiest to fix.

When the code is pushed to a branch in a source code repository, a workflow engine monitoring that branch will send a command to a builder tool to build the code and run the unit tests in a controlled environment. Oher quality checks, like unit test coverage, style check, and static analysis can happen at this stage. Finally, the builder tool creates one or more binary builds and other artifacts, images, stylesheets and documentes for the application.

 #### CD - Creating a staging environment

 Continuous delivery is the next phase, and entails deploying the application in a staging environment, which is a replica of the production stack, and running more functional tests. The staging environment could be a static environment premade for testing, or you could provision and configure a dynamic environment with commited infrastructure and configuration code for testing and deploying the application code.

 #### CD - Creating a production environment

 In the deployment/delivery pipeline sequencem after the staging environment, is the production environment, which is also built using infrastructure as code (IaC)

 #### Continuous deployment

 The final phase in the CI/CD pipeline is continuous deployment. This might include full automation of the entire software release process including deployment to the production environment. In a fully mature CI/CD environment, the path to the production environment is fully automated, which allows code to be deployed with high confidence.

 #### Maturity and beyond

 As your organization matures, it will continue to develop the CI/CD model to include the following improvements:

 - More staging environments for specific performance, compliances, security, and UI tests.
 - Unit test infrastructure and configuration code along with the application code.
 - Integration with other systems and processes such as code reviews, issue tracking and event notification.
 - Integration with database schema migration
 - Additional steps for auditing and business approval.

 Even the most mature organizations that have complex multi-environment CI/CD pipelines continue to look for improvements. DevOps is a journey, not a destination. Feedback is collected for continuous improvement. Having a single place to collaborate accross the teams, like, for example, Amazon CodeAnalyst, allows the teams to have visibility to build and deliver software products with confidence.

 ### Teams

 AWS recommends three different developer teams for implementing CI/CD: Application team, infrastructure team, and a tools team. This division has been used in fast-moving startups, large enterprise organizations, and Amazon itself.

 #### Application Team

 In charge of creating the application. They own the backlog, stories and unit tests, and they develope features based on a specified application target. This team's goal is to minimize the time these developers spend on non-core aplication tasks. Amazon CodeCatalyst allows the application team to maintain and manage issue tracking within the tool for collaboration.

 The application team should also have platform skills and undestanding of system configuration. This will enable the to focus on developing features and hardening the application

 ### Infrastructure team

 They write the code that both creates and configures the infrastructure needed to run the application. They are responsible for specifying what resources are needed, and work closely with the application team.

 This team should have skills in infrastructure provisioning methods, like AWS CDK, AWS CloudFormation or HashiCorp Terraform. The team may also need to develop configuration atomation skills with tools like Ansible and Puppet.

 ### Tools team

 They build and manage the CI/CD pipeline. They are responsible for the infrastructure and tools that make up the pipeline. This tools are both used by the application and the infrastructure team. The organization needs to continuously mature its tools team, so that the stay one step ahead of the maturing application and infrastructure teams.

 The team must be skilled in building and integrating all parts of the CI/CD pipeline. This includes building source control repositories, workflow engines, build environments, testing frameworks, and artifact repositories. The team may choose to implement tools such as Amazon CodeCatalyst, AWS CodePipeline as well as Jenkins, GitHub or other similar tools.

 Some organizations call this a DevOps team, but Amazon discourage this, thinking about DevOps as the sum of people, processes, and tools in software delivery.

 ## Testing stages in continuous integration and continuous delivery

 The three CI/CD teams should incorporate testing into the software development lifecycle at the different stages of the CI/CD pipeline. Overall, testing should start as early as possible.

 Mike Cohn introduced the following _Testing Piramid_ concept in _Succeding with Agile_.

 | Base  | Subbase                       | Middle                 | Peak |
 | ----- | ----------------------------- | ---------------------- | ---- |
 | Unit  | Service/Integration/Component | Performance/Compliance | UI   |
 | Fast  | ----------------------------- | ---------------------- | Slow |
 | Cheap | ----------------------------- | ---------------------- | Exp. |

 Unit tests are on the bottom of the pyramid. The are both the fastest to run and the least expensive. They should make up the bulk of your testing strategy. Around 70%. Unit tests should have near-complete code coverage, because bugs caught in this phase can be fixed quickly and cheaply.

 Service, component and integration test are above unit test on the pyramid. They require detailed environments, and therefore, are more costly in infrastructure requirements and slower to run. Performance and compliance tests are the next level. They require production-quality environments and are more expensive yet. UI and user acceptance tests are at the top of the pyramid, and require production-quality environments as well.

 All these tests are part of a complete strategy, to assure high quality software, but for speed in development, a focus on the bottom half of the pyramid is convenient.

## CI/CD implementation stages

### Setting up the source

At the beginning of the project is essential to set up a source where you can store the raw code and configuration schema changes. You can choose a code repository like GitHub, Amazon CodeCatalyst, or AWS CodeCommit.

### Setting up and running build tools

The build automation process is essential to CI. The first task of the build process would be to choose the correct tool for the build. Most of the right tools are:

- Ant, Maven, and Gradle for Java and Kotlin
- esbuild, Rollup, Webpack, and Vite for JavaScript and TypeScript.
- Cargo for Rust
- Go Build for Go
- Rake for Ruby

The best choice depends on the programming language of your project and the skill set of the team. After the build tool is chosen, all dependencies need to be clearly defined in the build scripts, along with the build steps. It's also best practice to version the final build artifacts, to make easier the deploy and keeping track of issues.

### Building

During the build stage, the build tools will take any change to the source code repository as input, build the software, and run the following types of tests:

__Unit Testing__: Tests a specific section of code to ensure the code does what it is expected to do. The unit testing is performed by the software developers during the development phase. At this stage, static code analysys, data flow analysis, code coverage, and other software verification processes could be applied.

__Static Code Analysis__: This test is executed without actually running the application, after the build and unit tests phase. This can help to find coding errors and security holes, and also can ensure conformance to coding guidelines.

__Static Application Security Testing (SAST)__: This is a test used to analyze code against security violations such as XML External Entity Processing, SQL Injection, and Cross Site Scripting. As soon as violations are detected, the build will fail and any progress will be blocked in the pipeline.

__Secrets Detection__: This check is used to identify secrets such as usernames, passwords and access keys in code. As soon as secrets are discovered, the build fails immediately.

__Software Composition Analisys (SCA)__: SCA tools enable users to manage and analyze the open-source components in their applications. They verify the licensing and asses security vulnerabilities. SCA tools can launch workflows to fix these vulnerabilities. Any finding that exceeds the defined threshold will fail the build and stop the progress on the pipeline.

__Software Bill of Materials(SBOM)__: A reporting mechanism to detail all the components and dependencies involved in the development and delivery of an application. It allows the visibility of the product's components, assures file integrity, leverages licensing governance, and provides a robust vulnerability scanning.

### Staging

In the staging phase, full environments are created that mirror the eventual production environment. The following tests are performed:

__Integration testing__: Verifies the interfaces between components against software design. Integration testing is an iterative process and facilitates building robusts interfaces and system integrity.

__Component testing__: Tests message passing between various components and their outcomes. A key goal of this testing could be idempotency in component testing. Tests can include extremely large data volumnes, or edge situations and abnormal inputs.

__System testing__: Tests the system end-to-end and verifies if the software satisfies the business requirement. This might include testing the user interface (UI), API, backend logic, and end state.

__Performance testing__: Determines the responsiveness and stability of a system as it performs under a particular workload. Performance testing is also used to investigate, measure, validate, or verify other quality attributes of the system, such as scalability, reliability, and resource usage. Types of performance tests might include load tests, stress tests, and spike tests. Performances tests are used for benchmarking against predefined criteria.

__Compliance testing__: Checks wheter the code change complies with the requirements of a nonfunctional specification and/or regulations. It determines if you are implementing and meeting the defined standards.

__User acceptance testing__: Validates e2e business flow. This testing is performed by an end user in a staging environment and confirms wheter the system meets the requirements of the requirement specification. Typically, customers employ alpha and beta testing (A/B testing) methodologies at this stage.

__Dynamic Application Security Testing (DAST)__: This type of testing is used to check for security problems in an applications while it is running. DAST tools evaluate the application by attacking like a malicious user would from the outside.

### Production

After passing the other tests, the staging phase is repeated in a production environment. In this phase, there is still a final Canary test by deploying the new code only on a small subset of servers or just in one, maybe on a specific AWS Region, before deploying the code to the entire production environment.

## Building the pipeline

This section discusses how to build the pipeline. It starts by establishing a pipeline with the minimum components needed for CI and then transition it later to a CD pipeline wit more components and stages. This section also discusses how you can consider using AWS Lambda functions and manual approvals for large projects, plan for multiple teams, branches and AWS Regions.

### Starting with a minimum viable pipeline for CI

The journey towards CD begins with a minimum viable pipeline (MVP). Teams can start with a very simple process, such as implementing a pipeline that performs a code style check, or a single unit test without deployment.

A key componente to help you build this pipeline is a `delivery orchestration tool`. **Amazon CodeCatalyst workflows** are CI/CD pipelines that enable you to easily build, test, and deploy applications. CodeCatalyst Workflows help you relaibly deliver high-quality applications updates frequently, quickly and securely. CodeCatalyst uses a visual editor or YAML to quickly assemble and configure actions to compose workflows that automate your CI/CD pipeline, test reporting and other manual processes. You can get started with a new project from scratch or by using a blueprint from a library of blueprints. If you use a blueprint, a default workflow will be created from the main branch of your repository, that you can then customize. To create a new workflow, once you launch a new project in Amazon CodeCatalyst, navigate to CI/CD > Workflows and create a new workflow.

CodeCatalyst supports many purpose build actions developed by AWS, as well as third parties such as GitHub Actions. To deploy an application or resoruce through CodeCatalyst, you can specify a deploy action inside the workflow. A _deploy action_ is a workflow building block that defines what you want to deploy, where you want to deploy it, and how you want to deploy it. Using deploy actions within a workflow, allows for the traceability, automatic rollbacks, and monitoring of your deployment as it progresses through the various stages  of your workflow and deployment.

AWS CodeCatalyst is a CI/CD service that can be used through the AWS Management Console for fast and reliable application and infrastructure updates. AWS CodePipeline builds, tests, and deploys your code every time the is a code change, based on the release process models you define. This enables you to rapidly and reliably deliver features and updates. Your can easily build out an end-to-end solution by sugin our pre-built plugins for popular third-parties services like GitHub, or by integrationg your own custom plugins into any stage of your release process. With AWS CodePipeline, you only pay for what you use. There are not upfront fees or long-term commitments.

The steps of AWS CodePipeline map directly to the source, build, staging, and production CI/CD stages. While CD is desirable, a simple two-steps pipeline that checks the source repository and performs a build action is near and useful goal.

For AWS CodePipeline, the source stage can accept inputs from GitHub, AWS CodeCommit, Atalassian Bitbucket, and Amazon Simple Storage Service (Amazon S3). Automating the build process is a critical first step for implementing CD and moving towards continuous deployment. Eliminating human involvement removes the burden from your team, minimizes errors introduces by manual packaging and allows you to start packaging consumable artifacts more often.

AWS CodePipeline works seamlessly with **AWS CodeBuild**, a `fully managed build service`, to make it easier to set up a build step within your pipeline that packages your code and runs unit tests. With AWS CodeBuild there is no need to provision, manage, or scale your own build servers. AWS CodeBuild scales continuously and processes multiple builds concurrently so your builds are not left waiting in a queue. AWS CodePipeline alos integrates with build servers like Jenkins, Solano CI, and TeamCity.

Once this stages are implemented, developer will get used to regularly pay attention to build and test results. They need to grow and maintain a healthy unit test base. This, in turn, bolsters the entire team's confidence in the CI/CD pipeline and furthers its adoption.

### Continuous delivery pipeline

Afte a CI pipeline has been implemented and supporting processes have been established, you teams can start trasitioning toward the continuous delivery pipeline. This transition requires teams to automate both building and deploying applications.

A continuous delivery pipeline is characterized by the presence of staging and production steps, where the production step is performed after a manual approval.

Teams can gradually start building a continuous delivery pipeline by writing their own deployment scripts.

Depending on the needs of an application, some of the deployment steps can be abstracted  by existing AWS services. For example, AWS CodePipeline directly integrates with **AWS CodeDeploy**, a service that automates code deployments to Amazon EC2 instances and instances running on premises.

AWS has detailed documentation on how to implement and integrate **AWS CodeDeploy** with your infrastructure and pipeline. If you are using Amazon CodeCatalyst, you should refer to the [documentation](https://docs.aws.amazon.com/codecatalyst/latest/userguide/deploy.html) for deploying using workflows.

You can add a deploy action (Like deploying to ECS) to your workflow that defines what you want to deploy, where you want to deploy it, and how you want to deploy it.

After your team successfully automates the deployment of the application, deployment stages can be expanded with various tests. For example you can add other out-of-the-box integrations, with services like Ghost Inspector, Runscope, and others.

### Adding Lambda actions

AWS CodePipeline supports integration with AWS Lambda. This enables implementing a broad set of tasks, such as creating custom resources in your environment, integrating third-party systems (like Slack), and performing checks on your newly deployed environment.

Lambda functions can be used in a CI/CD pipeline to do many tasks based on your needs. These are some examples:

- Roll out changes to your environment by applying or updating an AWS CloudFormation template.
- Create resources on demand in one stage of a pipeline using AWS CloudFormation and delete them in another stage.
- Deploy to Amazon Elastic Container (ECS) Docker Instances.
- Back up resources before building or deploying by creating an AMI snapshot.
- Add integration with third-party products to your pipeline, such as posting messages to an Internet Relay Chat (IRC) client.

### Manual approvals

Add an approval action to a stage in a pipeline at the point where you want the pipeline processing to stop so that someone with the required AWS **Identity and Access Management** (IAM) permissions can approve or reject the action.

If the action is approved, the pipeline processing resumes. If the action is rejected –or if no one approves or rejects the action within seven days of the pipeline reaching the action and stopping–  the result is the same as an action failing, and the pipeline processing does not continue.

### Deploying infrastructure code changes in a CI/CD pipeline

AWS CodePipeline lets you select AWS CloudFormation as a deployment action in any stage of your pipeline. You can then choose the specific action you would like AWS CloudFormation to perform, such as creating or deleting stacks and creating or executing change sets.

A **stack** is an AWS CloudFormation concept and represents a group of related AWS resources. While there are many ways of provisioning infrastructure as code (IaC), **AWS CloudFormation** is a comprehensive tool recommended by AWS as a scalable, complete solution that can describe the most comprehensive set of AWS resources as code. AWS recommmends using AWS CloudFormation in an AWS CodePipeline project to track infrastructure changes and tests.

### CI/CD for serverless applications

Amazon CodeCatalysts makes buiding CI/CD pipelines or workflows easy for serverless applications. You can use one of the serverless blueprints from the library of blueprints to kickstart a project within minutes.

You can use AWS CodePipeline, CodeBuild, and CloudFormation to build CI/CD pipeline for serverless applications. Serverless applications integrate managed services such as **Amazon Cognito**, **S3**, and **Dynamo DB** with event driven service, and AWS Lambda to deploy applications in a manner which doesn't require managing servers.

If you are a serverless application developer, you can use the combination of AWS CodePipeline, CodeBuild and CloudFormation to automate the building, testing, and deployment of serverless applications that are expressed in templates built with the AWS Serverles Applications model: [Rolling deployments for Lambda functions](https://docs.aws.amazon.com/lambda/latest/dg/lambda-rolling-deployments.html)

You can also create secure CI/CD pipelines that follow your organization´s best practises with [CDK Pipelines](https://docs.aws.amazon.com/cdk/v2/guide/cdk_pipeline.html) or AWS Serverless Application Model Pipelines ([SAM Pipelines](https://aws.amazon.com/blogs/compute/introducing-aws-sam-pipelines-automatically-generate-deployment-pipelines-for-serverless-applications/))

SAM Pipelines are a new feature of AWS SAM CLI that give you access to the benefits of CI/CD in minutes. They give you access to a set of default pipeline templates for AWS CodeBuild/CodePipeline that follow AWS deployment best practises.

### Pipelines for multiple teams, branches and AWS Regions

It is not uncommon, for multiple project teams, to work on different components. If multiple teams usa a single code repository, it can be mapped so that each team has its own branch. There should also be an integration or release branch for the final merge of the project. If it is a service-oriented or microservice architecture, each team could have its own repository.

In the first scenario, if a single pipeline is used it's possible that one team could affect the other's team progress by blocking the pipeline. 

> AWS recommends that you create specific pipelines for team branches and another release pipeline for the final product delivery.

### Pipeline integration with AWS CodeBuild

AWS CodeBuild is designed to enable your organization to build a highly available build process with almost unlimited scale. CodeBuild provides quickstart environments for a number of popular languages plus the ability to run any Docker container that you specify.

With the advantages of tight integration with AWS **CodeCommits**, CodePipeline, and **CodeDeploy**, as well as Git and CodePipeline actions, the CodeBuild service is highly flexible.

Software can be built through the inclusion of a buildspec.yml file that identifies each of the build steps, including pre- and post- build actions, or specified actions through the CodeBuild tool.

You can view detailed history of each build using the CodeBuild dashboard. Events are stored as **Amazon CloudWatch** log files.

### Pipeline integration with Jenkins

You can use the Jenkins build tool to create delivery pipelins. These pipelines use standard jobs that define steps for implementing continuous delivery stages. This is not optimal for larger projects because the current state of the pipeline doesn´t persist between Jenkins restarts, implementing manual approval is not straightforward, and tracking the state of a complex pipeline can be complicated.

AWS recomends that you use instead the [AWS Code Pipeline Plugin](https://wiki.jenkins-ci.org/display/JENKINS/AWS+CodePipeline+Plugin) for Jenkins. This plugin allows complex workflows to be described using Groovy-like domain-specific language and can be used to orchestrate complex pipelines. This plugin can also have its functionality enhanced by using satellite plugins like [Pipeline Stage View Plugin](https://plugins.jenkins.io/aws-codepipeline/), that helps you visualize the current progress of the defined stages of the pipeline, or [Pipeline Multibranch Plugin](https://plugins.jenkins.io/workflow-multibranch/), which groups builds from different branches.

It is recommended that you store your pipeline configuration in `Jenkinsfile` and have it checked into a source code repository. This allows for tracking changes to pipeline code and becomes even more important when working with the `Pipeline Multibranch Plugin`. AWS recommends that you divide your pipeline into stages. This logically groups the pipeline steps and also enables the Pipeline Stage View Plugin to visualize the current state of the pipeline.

### Deployment methods

In a CD process there are multiple strategies for rolling out new versions of software:

- Deploy in place:
  - If fails: Downtime, has 1x deploytime and zero deploymente downtime. Has some downtime when deployment is done. Requires DNS change, the rollback process is redeploy to the existing instance.
  - Consist in deploying the code of the application to an existing fleet of servers all at once.

- Rolling deploy:
  - If it fails, a single batch goes out of service. Any successful batches prior to failure running new application version. Require 2x times the deploy time. Zero deploy downtime. DNS changes. Rollback process is re-deploy. Code is deployed to existing instances.
  - Consist on deploying to a fleet, but dividing this fleet into portions, so that all of the fleet isn't upgraded at once. There are two software versions, new and old, running on the same fleet. If the deployment fails, only the updated portion of the fleet will be affected.

- Inmutable deploy:
  - Has a minimal impact when deployment fails. Takes x4 times the time of an in place deployment. Zero downtime and DNS change needed. The rollback process is by redeploying. Deployed to new instances.
  - Consists on starting an entire new set of servers with the new configuration or version of the application code. This pattern leverages the cloud capability that new server resources are created with simple API calls.

- Traffic splitting: 
  - Has minimal impact when deployment fails. Takes x4 times. No downtime and need DNS change. The rollback strategy is rerouting and terminating new instances. Deployment is to new instances.

- Blue/Green deployment:
  - Has minimal impact when deployment fails. Takes x4 times. Has zero downtime and does not require DNS change. Rollback strategy is to switch back to old environment. Deployment to a new instance.
  - Is similar to the inmutable deployment, but also requiring the creation of another environment. Once the new environment is up, traffic is shifted to the new deployment. Old environment is kept idle in case of a rollback needed. The idle environment is the "blue" environment.

- Canary release:
  - Is similar to rolling deployment but it is deployed to a small subset of the servers.

## Security in every stage of the CI/CD pipeline

Security must be applied to every component of the infrastructure, including CI/CD pipelines, from the moment a single line of code is written to the stages where it's deployed. That deployment can include multiple environments, identities, systems, and any applications which interact with it. During its journey, it's modified and updated continuously.

Every change needs to be monitored and made sure that it's safe to release towards the environment you are building. For every stage, there are multiple controls that can be embedded to the process whereas tool integrations are not sufficient by themselves for the secure CI/CD pipeline.

From the people, processes, and technology perspective:

- People delivering, handling, and monitoring the code, must have the awareness towards secure coding practices. They should stick to these guidelines and must never abandon them to deliver faster.

- Processes must be difend and reiterated continuously to make sure that your level of security is consistent across each and every stage of the pipeline.

- Technologies must be implemented to support the process mentioned above in each and every stage and must never be circumvented.

### Pre-commit hooks

They are scripts that are run at the developer's environment before a change to code is commited to the pipeline. They are controls that can be configured per general practices or company policies and any code update that is not compliant against those policies are blocked until they are corrected.

### IDE tools and plugins

Integrated Development Environment (IDE) is the tool most developers use to write their code. IDEs bring convenience to the developers with built-in or deployable plugins which can walk through the code, including, but not limited to, detecting potential issues, giving recommendations for improvements, linting, formatting, beautifying and securing it.

### Static Application Security Testing (SAST)

SAST, aka static analysis or static code analysis, are tools that detect bugs by analyzing the source code. SAST tools are built with the general approach of working backwards by dissecting the vulnerabilities to define possible attack methodologies and generate signatures against them to act as a preventative measure.

### Software Composition Analysis (SCA)

SCA is an automated process to identify the open-source packages that are in use within the code to define vulnerabilities and potential compliance-based issues. SCA tools identify open-source packages in an application and all the vulnerabilities that are present in them. They can also check the licenses for each package, check dependencies and bring infrastructure as code (IaC) manifests for potential vulnerabilities in contenarized environments.

### Dynamic Application Security Testing (DAST)

DAST tools are also named as black-box solutions. They test the applications during the lifecycle of their operations and give recommendations towards potential vulnerabilites and compliance issues. Since they monitor the behavior of the applications, they tend to generate less false positives compared to SAST tools.

### Interactive Application Security Testing (IAST)

IAST tools are a combination of SAST and DAST tools and embody both tools andvantages within. They are usually facilitated during the test and QA stages since it is the closest version of the production-level code. While running dynamically to identify the issues like a DAST tool, it will also be run inside the application server to evaluate the code like a SAST tool. The findings are real-time and IAST tools are also useful for API testing.

### Penetration testing

Penetration testing (Pentesting) aims to make sure that no vulnerability or non-compliant assets go unnoticed towards the end-product. Both tool and human based penetration testing methodologies are used towards applications and both have their benefits towards detecting vulnerabilities. Penetration testing should be done with a multi-directional approach while traversing the application to monitor and detect possible behaviors of the application and user experiences.


### Red/Blue/Purple teaming

Red/Blue/Purple teams are security experts with different roles to simulate real-life cyber-attacks. Their aim is to pinpoint system deficits, improve protection mechanisms and processes, and maximize the efficiency of the infrastructure while minimizing the risk. Red teams represent the attackers, blue teams operate as the defenders, and purple teams include members of both teams to fulfull a multi-faceted approach and bring various perspectives for security.

### Software Bill of Materials (SBoM)

SBoM is a complete, firnakky structured list of components, libraries and modules that are required to build a given piece of software and the supply chain relationships between them. In the US, SBoM are required in goverment contracts through and Executive Order.

#### Why is SBoM important?

SBoM serves three main purposes:
- **Intellectual property management**: IP Management of patents, copyrights, trade secrets, and source code. Export compliance, open-source license compliance, and regular audits are core components of the IP Management process.
- **Software Supply Chain Security**: What goes into your software is quite critical and placing proactive measures to avoid managing failures during the production phase. Continuous Vulnerability Management, implementation of End-Of-Life processes for software and building standarized high assurance systems are important steps towards building a Secure Software Supply Chain.S
- **Asset Management**: You cannot manage what you do not see, therefore to know and understand what your company has as assets, how they operate and interact individually and with each other is important to make improvements. It is also crucial to monitor and document all the assets to ensure only authorized parts are used to protect the supply chain.

> **Software Supply Chain**: Represents everything that is part of an application or interacts with it, during the entire software development life cycle (SDLC). IS is composed of components, libraries, tools, elements, sources, and processes with subcomponents, including but not limited to appliaction dependencies, container (operating system) packages, application package managers, OS package managers, unmanaged source files, unmanaged binaries, and snippets within propietary code.
> Security Risks towards any of those components will serve as the weakest link to the overall supply chain therefore it is vital to monitor and handle each component vigorously. Mitigating all chain threats may not be possible at first, but managing the risks and prioritizing them while applying general security practises will have a positive impact to the overall risk.
> _Some of this practises are_:
> - Apply leat privilege to resources across the software supply chain, enable multi-factor authentications and use strong passwords. Store passwords in encrypted password vaults and facilitate password-less authentication systems where applicable.
> - Increase employee security awareness with regular training, enablement sessions and game days.
> - Continuouesly monitor, update, and harden your devices. Isolate, prioritize and maintain systems with critical vulnerabilities.
> - Know, monitor, and assess your suppliers starting with DIrect (TIer-1) suppliers and going down the line by covering all your suppliers.
> - Implement secure coding practises and publish them internally for easy access so that they are used across the board and become as part of a developer's coding practise.
> - Apply security in every stage of the CI/CD pipeline.

## Database schema changes

It's common for modern software to have a database layer. While we do not recomment the use of relations DBs for new projects due to scaling and other issues, many existing projects use relational database technology and would like to adopt CI/CD.

When a relational database is used it's often necessary to modify the database in the continuous delivery process. Handling changes in a relational database requires special consideration, and it offers other challenges that the ones present when deploying application binaries.

Usually, when you upgrade an application binary, you stop the application, upgrade it, and then start it again. You do not bother about the application state.

When you are upgrading a database, you need to consider the state, because the database contains much state but comparatively little login and structure.

The database schema before and after a change is applied should be considered, as different versions of the database. You should use tools such as **Liquibase** and **Flyway** to manage the versions.

In genereal, these tools employ some variant of the following methods:
- Add a table to the database where a database version is stored.
- Keep track of database change commands, and bunch them together in versioned change sets. In the case of Liquibase, these changes are stored in XML files. FLyway employs a slightly different method where these change sets are handled as separate SQL files or, occasionally, as separate Java classes for more complex transitions.
- When Liquibase is beign asked to upgrade a database, it looks at the metadata table and determines which change sets to run in order to bring the database up-to-date with the latest version.

## Summary of best practices

**DO**:

- Treat your infrastructure as code:
  -Use version control for your infrastructure code.
  - Make use of bug tracking/ticketing systems.
  - Have peers review changes before applying them.
  - Test infrastructure code patterns/designs.
- Put developers into integrated teams of no more than 12 self-sustaining members.
- Have all developers commit code to the main branch frequently with no long-running feature branches.
- Consistently adopt a build system such as Maven or Gradel accross your organization and standardize builds.
- Brake security into your code pipeline.
- Have developers build unit tests toward 100% coverage of the code base.
- Ensure that unit tests are up-to-date and not neglected. Unit test failures should be fixed, not bypassed.
- Treat your continuous deleviery configuration as code.
- Establish role-based security controls(that is, who can do what and when):
  - Monitor/Track every resource possible.
  - Alert on services, availability, and response times.
  - Capture, learn, and improve.
  - Share access with everyone on the team.
  - Plan metrics and monitoring into the lifecycle.
- Keep and track standard metrics
  - Number of builds
  - Number of deployments
  - Average time for changes to reach production
  - Average time from the first pipeline stage to each stage
  - Average build time
- Use multiple distinct pipelines for each branch and team

**DON'T**:

- Have long-running branches with large complicated merges
- Have manual tests.
- Have manual approval processes, gates, code reviews, and security reviews
