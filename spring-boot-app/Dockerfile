FROM maven:3.6.0-jdk-8-slim AS build
COPY . /app
WORKDIR /app
RUN mvn clean package


FROM openjdk:8-jre-slim
COPY --from=build /app/target/spring-boot-app-1.0-SNAPSHOT.jar /spring-boot-app-1.0-SNAPSHOT.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","spring-boot-app-1.0-SNAPSHOT.jar"]