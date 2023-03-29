# Use the official Golang image as the build image
FROM golang:latest as builder

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . .

# Install any needed dependencies
RUN go get -d -v ./...

# Build the Go application
RUN go build -o /app/main .

# Use distroless as the base image
FROM gcr.io/distroless/base

# Set the environment variables
ENV PORT=3550

# Expose port 3550 for the application
EXPOSE 3550

# Copy the executable from the builder image
COPY --from=builder /app/main /

# Run the executable
CMD ["/main"]
