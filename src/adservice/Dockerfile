# Use a base image that includes Java and Gradle
FROM gradle:7.2.0-jdk11-hotspot AS build

# Set the working directory to the project directory
WORKDIR /app

# Copy the build.gradle and settings.gradle files
COPY build.gradle .
COPY settings.gradle .

# Copy the source code
COPY src/ src/

# Build the application
RUN gradle build --no-daemon

# Use a smaller base image for the final image
FROM adoptopenjdk:11-jre-hotspot

# Set the working directory to the root directory
WORKDIR /

# Copy the built JAR file from the previous stage
COPY --from=build /app/build/libs/myapp.jar .
EXPOSE 9555

# Run the application when the container starts
CMD ["java", "-jar", "myapp.jar"]



