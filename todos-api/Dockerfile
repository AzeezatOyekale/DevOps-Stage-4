# Node.js Todos API
FROM node:16
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8082
CMD ["node", "server.js"]







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
