FROM eclipse-temurin:22-jdk-jammy AS builder

WORKDIR /app

ADD demo/ .

RUN ./mvnw clean install


FROM eclipse-temurin:22-jdk-jammy

WORKDIR /app

EXPOSE 8080

COPY --from=builder /app/target/*.jar /app/app.jar

ENTRYPOINT ["java", "-jar", "/app/app.jar"]