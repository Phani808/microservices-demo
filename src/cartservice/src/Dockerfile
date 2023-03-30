# Use distroless base image for C
FROM gcr.io/distroless/cc-debian10

# Set the working directory to /app
WORKDIR /app

# Copy the source code to the container
COPY . .

# Compile the application
RUN cc -o app main.c

EXPOSE 7070

# Run the application
CMD ["./app"]
