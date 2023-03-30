# Build stage
FROM golang:1.17-alpine as builder

# Set the working directory to /app
WORKDIR /app

# Copy the Go module files
COPY go.mod go.sum ./

# Download dependencies
RUN go mod download

# Copy the source code into the container
COPY . .

# Build the application
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

# Final stage
FROM gcr.io/distroless/static

# Set the working directory to /app
WORKDIR /app

# Copy only the built binary from the builder stage
COPY --from=builder /app/app .
EXPOSE 8080

# Set the entrypoint to the built binary
ENTRYPOINT ["/app/app"]
