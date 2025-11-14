# Use an official Node.js runtime as a parent image
# Using Alpine Linux for a smaller image size
FROM node:20-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json (or npm-shrinkwrap.json)
# This leverages Docker's layer caching
COPY package*.json ./

# Install app dependencies
RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source inside the Docker image
COPY . .

# Make port 3001 available to the world outside this container
EXPOSE 3001

# Define the command to run your app using CMD which defines your runtime
CMD [ "node", "server.js" ]
