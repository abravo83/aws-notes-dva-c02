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