FROM maven:3.8.4-jdk-11-slim AS builder
COPY . .
WORKDIR /./src/
RUN mvn dependency:resolve
WORKDIR /.
RUN mvn package

FROM openjdk:8-jre-alpine
WORKDIR /./target/
CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
