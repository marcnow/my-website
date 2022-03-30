#Build jar file
FROM maven:3.8.4-jdk-8 as builder
LABEL stage = builder
COPY --chown=mvn:mvn . home/mvn/src
WORKDIR /home/mvn/src
RUN mvn clean package

#######
FROM openjdk:8
COPY --from=builder home/mvn/src/target/backend-0.0.1-SNAPSHOT.jar /
EXPOSE 8080/tcp
ENTRYPOINT [ "java", "-jar", "/backend-0.0.1-SNAPSHOT.jar" ]