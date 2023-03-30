# Base image
FROM openjdk:11

# Set the working directory
WORKDIR /app

# Copy the application jar file to the container
COPY target/my-app.jar /app/my-app.jar
EXPOSE 9555
# Set the command to run the application
CMD ["java", "-jar", "/app/my-app.jar"]
