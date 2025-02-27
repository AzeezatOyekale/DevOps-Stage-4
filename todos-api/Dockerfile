# Use official Node.js image (Node 8 is outdated, upgrading to Node 14)
FROM node:14-alpine

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json for better caching
COPY package*.json ./

# Install dependencies
RUN npm install --only=production

RUN npm install -g nodemon

# Copy the rest of the application
COPY . .

# Expose the application port
EXPOSE 8082

# Set default environment variables (can be overridden at runtime)
# ENV TODO_API_PORT=8082 \
#     JWT_SECRET=DZ5O1JxC96rER4wsvh4r2/bLPKhnrl2TbO5dFq9Kyas= \
#     REDIS_HOST=redis \
#     REDIS_PORT=6379 \
#     REDIS_CHANNEL=log_channel

# Start the application
CMD ["npm", "start"]







# # Use a Node.js base image (Updated to node:18 for better support)
# FROM node:8-alpine  

# # Set the working directory inside the container
# WORKDIR /app  

# # Copy package.json and package-lock.json first (for better caching)
# COPY package.json package-lock.json ./  

# # Install dependencies
# RUN npm install  

# # Copy the rest of the application files
# COPY . .  

# # Set environment variables (default values, can be overridden at runtime)
# ENV TODO_API_PORT=8082  
# ENV JWT_SECRET=foo  
# ENV REDIS_HOST=127.0.0.1  
# ENV REDIS_PORT=6379  
# ENV REDIS_CHANNEL=log_channel  

# # Expose the API port
# EXPOSE ${TODO_API_PORT}  

# # Start the API service
# CMD ["npm", "start"]
