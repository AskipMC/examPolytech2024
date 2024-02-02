FROM maven:3.9.6-eclipse-temurin-8 AS builder

WORKDIR /app

COPY . .

RUN mvn clean package -DskipTests 


FROM eclipse-temurin:8-jre

WORKDIR /app

LABEL maintainer="Matteo"

COPY --from=builder /app/target/*.jar back.jar

EXPOSE 8448

CMD ["java",  "-jar", "back.jar"]