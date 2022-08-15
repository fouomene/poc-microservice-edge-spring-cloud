FROM openjdk:11
MAINTAINER fouomene.com
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} microservice-commandes.jar
ENTRYPOINT ["java","-jar","/microservice-commandes.jar"]