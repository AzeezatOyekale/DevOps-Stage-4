# Use Node.js Alpine for a lightweight build
FROM node:14-alpine AS build-stage

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies efficiently

# RUN rm -rf package-lock.json node_modules
# RUN npm cache clean --force
RUN npm install

# Copy application source
COPY . .

# Build the Vue.js application
RUN npm run build

# Use Nginx for serving static files
FROM nginx:alpine AS production-stage

WORKDIR /usr/share/nginx/html


# Copy built app from previous stage
RUN rm -rf ./*


# Copy custom Nginx configuration
COPY --from=build-stage /app/dist ./


# Expose port 80
EXPOSE 80

# ENV PORT=80 \
#     AUTH_API_ADDRESS=http://auth:8081 \
#     TODOS_API_ADDRESS=http://todo:8082

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]








# # Use a Node.js base image
# FROM node:14-alpine  

# # Set the working directory inside the container
# WORKDIR /app  

# # Copy package.json and package-lock.json first (for better caching)
# COPY package.json package-lock.json ./  

# # Install dependencies
# RUN npm install  

# # Copy the rest of the application files
# COPY . .  

# # Expose the port (matches Vue's default: 8080)
# EXPOSE 8080  

# # Start the Vue.js development server
# CMD ["npm", "run", "dev"]  
