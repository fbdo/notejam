FROM openjdk:8u212-jdk
RUN addgroup --system spring && adduser --system spring && adduser spring spring
USER spring:spring
ARG JAR_FILE=target/app.jar
EXPOSE 8080
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java", "-XX:+UseContainerSupport", "-XX:InitialRAMPercentage=40.0", "-XX:MaxRAMPercentage=80.0", "-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]