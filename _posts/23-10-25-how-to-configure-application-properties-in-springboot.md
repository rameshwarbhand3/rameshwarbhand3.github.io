---
title: How to configure application properties in springboot application
date: 2023-10-25 11:47:10 -200
categories: [springboot,software,env variable,server]
tags: [servers,languages,variable]
---

## How to configure application properties in  springboot application

We can access environemnt variables in spring application in two ways.

1. By using @value annotation

2. By @ConfigurationProperties
3. By using environment variables


### By using @Value annotaion

1. We have to declare your variables in ```application.properties``` file in springboot application.
2. Suppose if you want to access this variable in your application we can simply used @Value annotation.
3.  e.g we have ```spring.first-name=abc```in your properties file.To read this from file we just used @Value and assigned variable and used it in your application.
```
@Value("${person.first-name})
private String firstName;
```

### By using @ConfigurationProperties annotaion
1. suppose we have number properties which we want to read from properties file, there we have to go for this approach.
2. we declared one class and add @ConfigurarionProperties & Configuration annotation.
3.  e.g we declared ```Class PersonConfig``` which has varaible like ```private String firstName```.
4. We can use this in your application by simply injecting object and access by using getter method.
```
@Autoowired
private PerosnConfig personconfig
```

### By using environment variable

 Suppose we have some properties in applcation.properties file. If you want to override this properties we can just edit configuration and add properties. 

 Spring boot automatically read override default configuration over properties we provide in edit configuration.