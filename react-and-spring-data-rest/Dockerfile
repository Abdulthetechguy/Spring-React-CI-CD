FROM openjdk:8-jre-alpine

COPY /target/*SNAPSHOT.jar app.jar
EXPOSE 8080
EXPOSE 80
ENTRYPOINT ["java","-jar","app.jar"]
