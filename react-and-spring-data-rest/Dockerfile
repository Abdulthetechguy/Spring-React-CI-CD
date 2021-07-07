FROM openjdk:8-jre-alpine

COPY /target/*SNAPSHOT.jar app.jar
ENV LANG en_GB.UTF-8
ENV JAVA_OPTS="-Xms512m -Xmx2048m"
EXPOSE 8080
EXPOSE 80
ENTRYPOINT ["java","-jar","app.jar"]
