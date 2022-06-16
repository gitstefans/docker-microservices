FROM alpine/git as sourcecode

RUN git clone https://github.com/kkenan/basic-microservices.git

FROM maven:3-openjdk-8-slim as build

RUN mkdir /build

WORKDIR /build

COPY --from=sourcecode /git/basic-microservices/spring-boot-app ./

RUN mvn clean package

FROM openjdk:8-jre-slim

RUN mkdir /app

WORKDIR /app

COPY --from=build /build/target/spring-boot-app-1.0-SNAPSHOT.jar ./

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "spring-boot-app-1.0-SNAPSHOT.jar"]