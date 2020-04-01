FROM openjdk:8-jdk-alpine
VOLUME /tmp
RUN addgroup -S spring && adduser -S spring -G spring
USER spring:spring
ARG JAR_FILE=target/app.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java", "-noverify", "-XX:TieredStopAtLevel=1", "-XX:+UnlockExperimentalVMOptions", "-XX:+UseCGroupMemoryLimitForHeap", "-XX:MaxRAMFraction=2","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]