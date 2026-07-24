# Implementing Microservices on AWS

> Notes on the AWS whitepaper on July 24th, 2026.
> This are just notes to help me follow the subject.
> Sometimes I just type the content to my notes without changing anything.
> Sometimes I resume, or substract what I consider non neccesary.
> Sometimes I expand on the text, usually to bring to the text some of the explanations embeded into figures.


MIcroservices offer a streamlined approach to software development that accelerates deployment, encourages innovations, enhances maintainability, and boosts scalabitily. This method relies on small, loosely coupled services that communicate through well-defined APIs, which are managed by autonomuos teams. Adopting microservices offers benefits, such as improved scalability, resilieance, flexibility, and faster development cycles.

This whitepaper explores three popular microservices patterns: API driven, event driven, and data streaming. We provide an overview of each approach, outline microservices key features, adress the challenges in their development, and illustrate how AWS can help application teams tackle these obstacles.

Considering the complex nature of topics like data store, asynchronous communication, and service discovery, you are encouraged to weigh your application's specific needs and use cases alongside the guidance provided when making architectural decisions.

## Introduction

Microservices architectures combine successful and proven concepts from various fields, such as:

- Agile software development
- Service-oriented architectures
- API-first design
- Continuous integration/Continuous delivery

Often, microservices incorporate design patterns from the [Twelve-Factor App](https://12factor.net/).

Even though microservices offer many benefits, it is still important to assess your use case and associated costs. Monolithic architectures or alternative approaches may be more appropiate in some cases. Deciding between microservices or monoliths should be made on a case-by-case analysis, considering scale, complexity, and specific use cases.

We first explore a highly scalable, fault-tolerant microservices architecture (user interface, microservices implementation, data store), and demonstrate how to build it on AWS using container technologies. We then suggest AWS services to implement a typical serverless microservices architecture, reducing operational complexity.

Serverless is characterized by the following principles:
- No infrastructure to provision or manage.
- Automatically scaling by unit of consumption
- "Pay for value" billing model
- Built-in availability and fault tolerance
- Event Driven Architecture (EDA)

Lastly, we examine the overall syste, and discuss cross-service aspects of a microservices architecture, such as distributed monitoring, loggin, tracing, auditing, data consistency, and asynchronous communication.

This document focuses on workloads running in the AWS Cloud, excluding hybrid scenarios and migration strategies. For information on migration strategies, refere to the [Container Migration Methodology whitepaper](https://d1.awsstatic.com/whitepapers/container-migration-methodology.pdf).

## Are you Well-Architected?

The AWS Well-Architected Framework helps you understand the pros and cons of the decisions you make when building systems in the cloud. The six pillars of the Framework allow you to learn architectural best practises for designing and operating reliable, secure, efficient, cost-effective and sustainable systems. Using the AWS Well-Architedted Tool, free of charge in the AWS Management Console, you can revier your workload against these best practises by ansering a set of questions on each pillar.

In the [Serverless Application Lens](https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/welcome.html), we focus on the best practises for architecting your serverless applications on AWS.

## Modernizing to microservices

Microservices are essentially small, independent units that make uo an application. Transitioning from traditional monolithic structures to microservices can follow [various strategies](https://docs.aws.amazon.com/prescriptive-guidance/latest/modernization-decomposing-monoliths/decomposing-patterns.html)

This transition also impacts the way your organization operates:
- It encourages agile development, where teams work in quick cycles.
- Teams are typically small, sometimes described as _two-pizza teams_.
- Teams take full responsability for their services, from creation to deployment and maintenance.

## Simple microservices architecture on AWS

Typical monolithic applications consist of different layers: a presentation layer, an application layer and a data layer.

Microservices, on the other hand, separate functionalities into cohesive verticals according to specific domains, rather than technological layers. Figure 1 ilustrates a reference architecture for a typical microservice application on AWS:

> Description of figure 1
> Imagine three columns, this colums are at the same time containes, they hold different services, grouped by functional subject: User Interface, Compute Implementation, and Data Store (Basically the same MVC model from the monolith)
> Inside the first column, **User interface**, we found two services: Amazon CloudFront, Amazon S3.
> Inside the second column, **Compute integration**, we find another two services: ALB and  Amazon ECS
> Inside the third column, **Data Store**, we find three services: Amazon ElastiCache, Amazon Aurora, and Amazon DynamoDB.

