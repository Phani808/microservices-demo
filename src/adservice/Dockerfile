# Use the official image as a parent image
FROM openjdk:11-jre-slim

# Set the working directory to /app
WORKDIR /app
RUN apt-get -y update && apt-get install -qqy

# Copy the Gradle files
COPY build.gradle .
COPY gradlew .

# Copy the source code
COPY src src

# Run Gradle to build the application
RUN ./gradlew build --no-daemon

# Expose port 8080
EXPOSE 9555

# Run the application
CMD ["java", "-jar", "build/libs/your-application-name.jar"]
