# Use the official Golang image as the base image
FROM golang:latest

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed dependencies
RUN go get -d -v ./...

# Set the environment variables
ENV PORT=3550

# Expose port 8080 for the application
EXPOSE 3550

# Build the Go application
RUN go build -o main .

# Run the executable
CMD ["/app/main"]
