---
title: How to deploy your webapp on tomcat with AWS EC2 and RDS 
date: 2023-10-25 18:47:10 -200
categories: [Iaas,software,virtual machine,server]
tags: [servers,languages,Infrastructure]
---

In this blog  I am going to show you we can deploy our application using Amazon Ec2 and RDS. For this we need Amazon web services Ec2 and Rds services. 

## Steps to deploy your application on AWS EC2 and RDS Service

1. Create a free tier account on aws and select region. I will follow this tutorial  [create account](https://www.youtube.com/watch?v=xi-JDeceLeI&list=PLpLBSl8eY8jQJ97s0BepJco73zCgbG_VP&index=16).

2. To run your application you required virtual machine. We can create this by using [create EC2 instance](https://www.youtube.com/watch?v=uI2iDk8iTps&list=PLpLBSl8eY8jQJ97s0BepJco73zCgbG_VP&index=9).

3. We required relational database to connect your application.We can create this by using [create RDS](https://www.youtube.com/watch?v=87seroYw8iI&list=PLpLBSl8eY8jQJ97s0BepJco73zCgbG_VP&index=22).Here  i will select mysql database instance.

4. Now our both services running on aws.

5. Go to our application in eclipse or intellijId and convert into war or jar file. but make sure to  remember edit database configuration detail as per your ```RDS```before going to convert into war file.

6. Install tomcat server on your ec2 service by using [Install tomcat](https://medium.com/@raguyazhin/step-by-step-guide-to-install-apache-tomcat-on-amazon-linux-120748a151a9) follow the step by step guide.

7. Go to root directory on ec2 instance and use command ```sh startup.sh``` it will run your tomcat server on ec2 on port 8080.

8. You can access your tomcat server use public network Ip of your instance and run tomcat on your local by ```http://server_ip:8080```.

9. Deploy your application on tomcat server i.e deploy your war file on tomcat and check your database running on RDS should be connected.

10. And that's it by this way we can deploy our application on ```AWS CLOUD``` as a infrastructure without maintaining on premises server and database.