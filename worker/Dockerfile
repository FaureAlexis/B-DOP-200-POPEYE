FROM maven:3.8.4-jdk-11-slim AS builder
COPY . .
WORKDIR /./src/
RUN mvn dependency:resolve
WORKDIR /.
RUN mvn package

FROM openjdk:11-jre-slim
WORKDIR /./target/
CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
