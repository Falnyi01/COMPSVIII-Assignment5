# Use Node 18-alpine as base image
FROM node:18-alpine

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Build production application
RUN npm run build

# Use nginx to serve built files
FROM nginx:alpine
COPY --from=0 /app/dist /usr/share/nginx/html

# Expose port 80 for frontend server (nginx default port)
EXPOSE 80

# Start nginx server
CMD ["nginx", "-g", "daemon off;"]