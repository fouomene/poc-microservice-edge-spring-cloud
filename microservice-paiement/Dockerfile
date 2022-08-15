FROM openjdk:11
MAINTAINER fouomene.com
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} microservice-paiement.jar
ENTRYPOINT ["java","-jar","/microservice-paiement.jar"]