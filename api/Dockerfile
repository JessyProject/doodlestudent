FROM maven:3.8.2-jdk-11 AS build
WORKDIR /app
COPY . .
RUN mvn package -DskipTests=true -Dquarkus.package.type=uber-jar
CMD ["java", "-jar", "/app/target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar"]

FROM openjdk:11-jdk-alpine
COPY --from=build target/*.jar app.jar
CMD [ "java", "-jar", "project/target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar" ]