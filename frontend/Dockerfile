FROM node:14

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 8080

CMD ["npm", "run", "dev"]






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
