## What is it?
This source code is an Spring Boot web application (mvc + thymeleaf).
 
Tested with
* Docker 19.03
* Ubuntu 19
* Java 8 or Java 11
* Spring Boot 2.2.4.RELEASE
* Maven

For explanation, please visit this article - [Docker and Spring Boot](https://mkyong.com/docker/docker-spring-boot-examples/)

## How to run this?
## make sure DOCKER_DEFAULT_PLATFORM is not set
```bash
$ sdk install java 11.0.20-amzn
$ export DOCKER_DEFAULT_PLATFORM=
$ git clone https://github.com/ragsns/docker-java
$ cd docker-spring-boot
$ mvn clean package
$ java -jar target/spring-boot-web.jar

  access http://localhost:8080

//dockerize

// create a docker image
$ sudo docker build -t spring-boot:1.0 .
// for multi-arch
$ docker buildx build --no-cache \
--push \                  
--platform linux/arm/v7,linux/arm64/v8,linux/amd64 --tag ragsns/spring-boot-multi .
// run it
$ sudo docker run -d -p 8080:8080 -t spring-boot:1.0

  access http://localhost:8080
```
