FROM eclipse-temurin:22-jdk-jammy

WORKDIR /app

ADD demo/ .

RUN ./mvnw clean install

EXPOSE 8080

CMD ["java", "-jar", "/app/target/demo-0.0.1-SNAPSHOT.jar"]