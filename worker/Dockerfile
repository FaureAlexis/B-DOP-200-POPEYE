FROM maven:3.8.4-jdk-11-slim AS builder
COPY . .
RUN mvn dependency:resolve
RUN mvn package

FROM openjdk:11-jre-slim
WORKDIR /target
COPY --from=builder /target .
CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]