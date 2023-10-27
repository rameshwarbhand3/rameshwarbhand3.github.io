---
title: How to read and override application properties in springboot
date: 2023-10-25 11:47:10 -200
categories: [springboot,software,env variable,server]
tags: [servers,languages,variable]
---

## How to read and override application properties in the springboot

We can access application properties as variables in spring boot by following ways.

1. By using @value annotation
2. By @ConfigurationProperties

We will use below example to explain
```
person.first-name=Rameshwar
person.last-name=Bhand
person.full-name=Rameshwar Bhand
```

### By using @Value annotaion


1. Suppose if we want to access any of the property and inject it as variable in your application code(Controller or Service classes)then  we can simply used @Value annotation.
2.  e.g we have `person.first-name=abc` in your properties file.To read this from file we just used @Value and assigned variable and used it in your application.
    ```
    @Value("${person.first-name})
    private String firstName;
    ```

### By using @ConfigurationProperties annotaion
1. Supposing we have a number of properties that we want to read from the properties file, we have to go with this approach.
2. We can declare a class with the @ConfigurationProprties annotation along with the @Configuration annotation.
3. we can declare `Class PersonConfig` which map the property like `person.xxx` to the equivalent variable variable like for e.g. `private String firstName`.

   Below is a complete class example to map the properties with person prefix to the java class

    ``` java
    @Getter
    @Setter
    @ConfigurationProperties(prefix = "person")
    @Configuration
    public class PersonConfig {
        private String firstName;
        private String lastName;
        private String fullName;
    }
    ```
4. Now In order to use it in the application we can by simply inject the `PersonConfig` object and access it by using getter method.
    ```
    @Autowired
    private PerosnConfig personconfig;
    ```

## Override app config properties using environment variable

If  we want to override person properties per deployment of the application we can do so by environment variable 
 
  As mention in the above example of application properties lets say we want to override person related config properties.

  ```
  PERSON_FIRST_NAME=John
  PERSON_ LAST_NAME=Kenny
  PERSON_FULL_NAME=JOHN Kenny
  ```
 Spring boot automatically read and override default configuration.