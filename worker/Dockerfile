FROM maven:3.5-jdk-8-alpine AS builder
WORKDIR .
RUN mvn dependency:resolve
WORKDIR src/
RUN mvn package

FROM openjdk:8-jre-alpine
RUN java -jar worker-jar-with-dependencies.jar
