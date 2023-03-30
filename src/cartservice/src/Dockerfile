# Use an appropriate base image
FROM gcc:latest

# Set the working directory to /app
WORKDIR /app

# Copy the source code to the container
COPY . .

# Compile the application
RUN gcc -o app main.c

EXPOSE 7070

# Run the application
CMD ["./app"]
