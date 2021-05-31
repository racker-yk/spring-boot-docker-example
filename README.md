# Spring Boot Docker Example

### Build the project
```bash
$ ./mvnw package
```
OR
```bash
$ mvn clean package
```

### Build the docker image
```bash
$ docker build -t springio/gs-spring-boot-docker .
```

### Run the docker image
```bash
$ docker run -p 8080:8080 springio/gs-spring-boot-docker
```

Open another terminal and use below command
```bash
$ curl localhos:8080
```
OR open in the browser the above link.

### Docker file
```dockerfile
FROM openjdk:8-jdk-alpine

ARG JAR_FILE=target/*.jar

COPY ${JAR_FILE} app.jar

ENTRYPOINT ["java","-jar","/app.jar"]
```
The image size of above docker and libraries is `122MB` 