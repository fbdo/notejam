FROM openjdk:8-jdk-alpine
RUN addgroup -S spring && adduser -S spring -G spring
USER spring:spring
ARG JAR_FILE=target/app.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java", "-Xmx896m", "-XX:MaxRAM=1073741824", "-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]