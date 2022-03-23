FROM maven:3.8.2-jdk-11 AS build
WORKDIR /project
COPY . /project/
RUN mvn package -Dquarkus.package.type=uber-jar -Dmaven.test.skip=true

FROM openjdk:11-jdk-alpine
COPY --from=build target/*.jar app.jar
CMD [ "java", "-jar", "tlcdemoApp-1.0.0-SNAPSHOT-runner.jar" ]

