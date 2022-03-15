FROM maven:3.5-jdk-8-alpine AS builder
COPY . .
WORKDIR /./src/
RUN mvn dependency:resolve
WORKDIR /.
RUN mvn package

FROM openjdk:8-jre-alpine
WORKDIR /./target/
CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
