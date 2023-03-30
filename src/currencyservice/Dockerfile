# Use an appropriate base image
FROM node:latest

# Set the working directory to /app
WORKDIR /app
RUN apk add --update --no-cache \
    python \
    make \
    g++
# Copy the package.json and package-lock.json files to the container
COPY package*.json ./

# Install the application dependencies
RUN npm install

# Copy the source code to the container
COPY . .

# Expose port 3000
EXPOSE 7000

# Run the application
CMD ["npm", "start"]
