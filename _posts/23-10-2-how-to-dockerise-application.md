---
title: Docker
date: 2023-10-02 15:30:10 -800
categories: [Container,VPN,Webapp]
tags: [Containarisation,build,deploy]
---


## What is Container?
A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. 

## What is Docker?
A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

## How to dockerise your  springboot and mysql app using docker-compose?

Sure, I can help you with that. Docker is a great tool for containerizing and deploying applications, and it can be used to containerize a ```Spring Boot``` project along with a ```MySQL``` database.

Here are the steps to dockerize a ```Spring Boot``` project with ```MySQL```:

1. First, make sure you have Docker installed on your machine.

2. Create a ```Dockerfile``` in the root directory of your Spring Boot project. The Dockerfile will contain instructions for building a ```Docker image``` of your application. Here is an example ```Dockerfile```:

```
FROM openjdk:11-jre-slim
WORKDIR /app
COPY target/my-spring-boot-app.jar my-spring-boot-app.jar
CMD ["java", "-jar", "my-spring-boot-app.jar"]
```

This Dockerfile uses the openjdk:11-jre-slim base image, sets the working directory to /app, copies the Spring Boot application JAR file into the container, and sets the command to run the JAR file.

```
version: '3'
services:
  db:
    image: mysql:8.0
    restart: always
    environment:
      MYSQL_DATABASE: mydb
      MYSQL_USER: myuser
      MYSQL_PASSWORD: mypassword
      MYSQL_ROOT_PASSWORD: rootpassword
  app:
    build: .
    restart: always
    ports:
      - 8080:8080
    depends_on:
      - db
    environment:
      SPRING_DATASOURCE_URL: jdbc:mysql://db:3306/mydb?useSSL=false
      SPRING_DATASOURCE_USERNAME: myuser
      SPRING_DATASOURCE_PASSWORD: mypassword
```

This docker-compose.yml file defines two services: a MySQL database and the Spring Boot application. The db service uses the official MySQL 8.0 image and sets environment variables for the database name, username, and password. The app service builds the Docker image using the Dockerfile in the current directory, sets the container port to 8080, and sets environment variables for the database connection information.

1. Build the Docker image by running the following command in the root directory of your project:

```
docker-compose build
```
This will build the Docker image for your Spring Boot application.

2. Start the Docker containers by running the following command in the root directory of your project:

```
docker-compose up
```
This will start the MySQL database container and the Spring Boot application container.

That's it! Your Spring Boot application and MySQL database are now running inside Docker containers. You can access your application by navigating to [http://localhost:8080](http://localhost:8080) in your web browser.
