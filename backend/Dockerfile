# Use Node 18-alpine as base image
FROM node:18-alpine

# Set working directory insde the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

#Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Create a directory for SQLite database
RUN mkdir -p ./db

# Expose port 5000 for backend server
EXPOSE 5000

# Start the backend server
CMD ["npm", "start"]