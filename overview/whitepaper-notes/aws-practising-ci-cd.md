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