# Stage 1: Build the application
FROM gradle:7.2.0-jdk11 AS build
WORKDIR /app
COPY build.gradle .
COPY src src
RUN gradle build --no-daemon

# Stage 2: Run the application
FROM openjdk:11-jre-slim
WORKDIR /app
COPY --from=build /app/build/libs/my-app.jar .
EXPOSE 9555
CMD ["java", "-jar", "my-app.jar"]
