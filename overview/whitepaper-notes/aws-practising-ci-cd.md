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