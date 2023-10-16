---
title: Springboot
date: 2023-10-11 15:30:10 -800
categories: [Java,framework]
tags: [Web,Server,Maven,Tomcat,Mvc,spring,mysql]
---

## What is Springboot?

Java Spring Boot is an open-source tool that makes it easier to use Java-based frameworks to create microservices and web apps.


Nowadys React and Spring Boot are two of the hottest technologies for developing Full Stack applications.



## Features

* Create stand-alone Spring applications

* Embed Tomcat, Jetty or Undertow directly (no need to deploy WAR files)

* Provide opinionated 'starter' dependencies to simplify your build configuration

* Automatically configure Spring and 3rd party libraries whenever possible

* Provide production-ready features such as metrics, health checks, and externalized configuration

* Absolutely no code generation and no requirement for XML configuration

## How does it work?

Spring Boot automatically configures your application based on the dependencies you have added to the project by using ```@EnableAutoConfiguration``` annotation. For example, if MySQL database is on your classpath, but you have not configured any database connection, then Spring Boot auto-configures an in-memory database.

The entry point of the spring boot application is the class contains ```@SpringBootApplication``` annotation and the main method.

Spring Boot automatically scans all the components included in the project by using ```@ComponentScan``` annotation.

## Spring Boot Starters

For example, if you want to use Spring and JPA for database access, it is sufficient if you include spring-boot-starter-data-jpa dependency in your project.

For e.g.

* Spring Boot Starter Actuator dependency is used to monitor and manage your application. Its code is shown below −

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```
* Spring Boot Starter Security dependency is used for Spring Security. Its code is shown below −

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-security</artifactId>
</dependency>
```

* Spring Boot Starter web dependency is used to write a Rest Endpoints. Its code is shown below −

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```
* Spring Boot Starter Thyme Leaf dependency is used to create a web application. Its code is shown below −

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>
```

* Spring Boot Starter Test dependency is used for writing Test cases. Its code is shown below −

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-test</artifactId>
</dependency>
```

## Spring boot flow architecture


![Alt text](https://media.geeksforgeeks.org/wp-content/uploads/20190822182410/Spring-Boot-flow-architecture.jpg)


