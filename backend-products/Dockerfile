FROM maven:3.8.3-openjdk-17 AS build
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:17-slim
COPY --from=build /target/backend-products-0.0.1-SNAPSHOT.jar backend-products.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "backend-products.jar"]