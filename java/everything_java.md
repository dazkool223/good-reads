## Overview of Java and its ecosystem
 - Differences between Java and JavaScript 
 - Setting up the development environment (JDK, IDEs)
 - Java program structure Data types and variables 
 - Operators and expressions 
 - Control flow statements (if-else, switch, loops)

## Object-Oriented Programming in Java
- Classes and objects
- Constructors
- Methods
- Encapsulation
- Inheritance
- Polymorphism
## Core Java APIs
- String handling(Builder/buffer)
- Collections framework (List, Set, Map)
- Generics
- Exception handling
- Input and Output (I/O) (java neo)
- Java Streams and Lambda expressions (YouTube ref : vyankat subramanyam https://www.youtube.com/playlist?list=PLPRXAxv_6nu9aUFAC8_02xQgYQLCoEGEi )

## Working with Databases
- JDBC (Java Database Connectivity)
- CRUD operations
- Connection pooling
- ORMs (e.g., Hibernate)
- Spring Data JPA

## Java Development Tools
- Build tools (Maven, Gradle)
- Unit testing with JUnit (WireMock)
- Debugging in Java

## Web Development with Spring Boot
- Spring Boot https://www.youtube.com/playlist?list=PLqq-6Pq4lTTbx8p2oCgcAQGQyqN8XeA1x
- Dependency Injection (why constructor injection is recommended over field injection? )
- bean lifecycle & types of bean configuration and creation
- Spring MVC architecture.
- Creating REST APIs with Spring Boot
- JSON processing with Object Mapper
- Consuming RESTful web services
- @ControllerAdvice for exception handling
- @RestExchange to handle middleware to backend calls
- Spring JPA
- Spring scheduler/ cron job

## Advanced Java Concepts
This part of learning java is optional for beginners. You can learn these as you progress through the software development career
- Multithreading and concurrency
- Java Memory Management (Garbage Collection)
- Annotations
- Reflection API
- virtual threads

## Design Patterns
- Common design patterns (Singleton, Factory, Observer, etc.) ( really cool website to learn design patterns : https://refactoring.guru/)
- Effective Java programming practices
- Code readability and maintainability
## Deployment
- Packaging Java applications (JAR, WAR)
- Application servers (Tomcat, Jetty)
- Cloud deployment basics (AWS, Azure)

## Other Technologies used in Qualys
- Liquibase - Handle database change management
- Kafka - real time data streaming
- OracleDB
- Prometheus/ Grafana - microservice monitoring and metrics
- vault by hashicorp - store secrets
- consul by hashicorp - store microservice configurations
- blackduck - vulnerability management in dependencies
- coverity - code scanning for vulnerabilities
- ReactJS - frontend applications
- Service mesh architecture for service to service communication

## Project implementation :
**Objective**
Develop a backend system to manage the flow of orders, payments, and notifications using Spring Boot. The system will enable users to place orders, process payments, and receive notifications about their order status. These services should communicate through Rest APIS and rely on kafka for async event driven processing. Store order and payment details using a relational database (e.g., PostgreSQL on local docker or any relational db of your choice). Use JPA and Spring Data for database interactions.

**Order Service**
- Create, update, and retrieve orders.
- Track order status (e.g., Pending, Paid, Shipped).
- send a message on kafka topic about order creation

**Payment Service**
- Process payments for orders.
- Validate payment details.
- Update order status after successful payment.
- Send a message to kafka topic about payment success

**Notification Service**
- consume message for payment service upon payment success
- consume message for order service upon order creation

## Additional Resources
- **Clean Code** by R Martin
- Effective Java" by Joshua Bloch
- "Java: The Complete Reference" by Herbert Schildt
- Official documentation (Oracle Java Documentation)
- Microservices Patterns by Chris Richardson -> Must read for microservices, system design!
- Designing Data Intensive Applications by Martin Klepmann -> Must read for system design!
- Martin Fowler on Event Driven(Event Notification, Event carried state transfer, Event sourcing, CQRS)
- Gaurav Sen playlist for System Design
- Talk about Database Indexing
- SOLID principles
- Multithreading