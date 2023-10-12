---
sidebar_position: 1
---

# Run Users Microservice and Albums Microservice using command-line

## 1) Clone the project
```bash
git clone https://github.com/webuxmotion/aws-ecs-course-users-microservice.git
```

## 2) Package the project into jar archive

```bash
mvn clean package
# run the project
mvn spring-boot:run -Dspring-boot.run.arguments=--spring.profiles.active=dev
```
Check the site [http://localhost:8081/actuator/health](http://localhost:8081/actuator/health)

You should see like this:
**{"status":"UP"}** in browser

## 3) Clone the second project
```
git clone https://github.com/webuxmotion/aws-ecs-course-albums-microservice.git
```
## 4) Package the second project into jar archive

```bash
cd aws-ecs-course-albums-microservice
mvn clean package
# run the project
mvn spring-boot:run -Dspring-boot.run.arguments=--spring.profiles.active=dev
```
Check the site [http://localhost:8080/actuator/health](http://localhost:8080/actuator/health)

You should see like this:
**{"status":"UP"}** in browser
