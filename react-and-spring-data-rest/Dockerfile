# FROM openjdk:8-jre-alpine

# COPY /target/*SNAPSHOT.jar app.jar
# ENV LANG en_GB.UTF-8
# ENV JAVA_OPTS="-Xms512m -Xmx2048m"
# # EXPOSE 8080
# # EXPOSE 80
# ENTRYPOINT ["java","-jar","app.jar"]
FROM maven:3.6.1-jdk-8-slim AS build
RUN mkdir -p workspace
WORKDIR /workspace
COPY ./ /workspace
RUN mvn -f pom.xml clean install -DskipTests=true
FROM openjdk:8-alpine
COPY --from=build /workspace/target/*SNAPSHOT.jar app.jar
ENV LANG en_GB.UTF-8

ENV JAVA_OPTS="-Xms512m -Xmx2048m"
EXPOSE 8080
#ENTRYPOINT ["java","-jar","app.jar"]
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","app.jar"]
