FROM maven:3-eclipse-temurin-21 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

FROM eclipse-temurin:21-alpine
WORKDIR /app
COPY --from=build /app/target/merchandiseMgmtERP.jar app.jar
EXPOSE 8089
CMD ["java", "-jar", "app.jar"]