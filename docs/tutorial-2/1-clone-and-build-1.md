---
sidebar_position: 1
---

# Run Users Microservice and Albums Microservice using command-line

## 1) Clone the project
```bash
git clone https://github.com/webuxmotion/aws-ecs-course-users-microservice.git
cd aws-ecs-course-users-microservice
```

## 2) Package the project into jar archive

```bash
mvn clean package
# run the project
mvn spring-boot:run -Dspring-boot.run.arguments=--spring.profiles.active=dev
```
Check the site [http://localhost:8081/actuator/health](http://localhost:8081/actuator/health)

In browser you should see text like this:
**{"status":"UP"}**

## 3) Clone the second project
```bash
git clone https://github.com/webuxmotion/aws-ecs-course-albums-microservice.git
cd aws-ecs-course-albums-microservice
```
## 4) Package the second project into jar archive

```bash
mvn clean package
# run the project
mvn spring-boot:run -Dspring-boot.run.arguments=--spring.profiles.active=dev
```
Check the site [http://localhost:8080/actuator/health](http://localhost:8080/actuator/health)

In browser you should see text like this:
**{"status":"UP"}**
