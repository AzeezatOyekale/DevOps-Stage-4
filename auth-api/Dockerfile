# Build Stage
FROM golang:1.23 AS builde-stage

# Set working directory
WORKDIR /app

# Copy go.mod and go.sum and download dependencies
COPY go.mod go.sum ./
RUN go mod download

# Copy the source code
COPY . .

# Build the Go application
RUN CGO_ENABLED=0 GOOS=linux go build -o auth-api .

# Final Stage: Create a minimal runtime image
FROM alpine:latest

# Set working directory
WORKDIR /app

# Copy the built binary from the build stage
COPY --from=builde-stage /app/auth-api .

# Expose the application port (default to 8081)
EXPOSE 8081

# Set default environment variables (can be overridden at runtime)
# ENV AUTH_API_PORT=8081 \
#     USERS_API_ADDRESS=http://user:8083 \
#     JWT_SECRET=DZ5O1JxC96rER4wsvh4r2/bLPKhnrl2TbO5dFq9Kyas=

# Run the application
CMD ["./auth-api"]




# # Use a minimal Go base image
# FROM golang:1.21-alpine

# # Set the working directory inside the container
# WORKDIR /app  

# # Copy Go module files first (for better caching)
# COPY go.mod go.sum ./

# # Download dependencies
# RUN go mod download  

# # Copy the rest of the application files
# COPY . .  

# # Build the Go application binary
# RUN go build -o auth-api  

# # Expose the authentication API port (defined by ENV)
# EXPOSE ${AUTH_API_PORT}  

# # Set environment variables (optional, can be overridden at runtime)
# ENV AUTH_API_PORT=8081  
# ENV USERS_API_ADDRESS=http://users-api:8083  
# ENV JWT_SECRET=your-secret-here  

# # Start the authentication API service
# CMD ["./auth-api"]




