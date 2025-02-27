# Java Spring Boot Users API
FROM maven:3.8.6-openjdk-11 AS builder
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn package -DskipTests

FROM openjdk:8-jre-slim
WORKDIR /app
COPY --from=builder /app/target/*.jar ./users-api.jar
EXPOSE 8083
CMD ["java", "-jar", "users-api.jar"]








# # Use OpenJDK 17 as base image
# FROM openjdk:17-jdk-slim  

# # Set the working directory inside the container
# WORKDIR /app  

# # Copy Maven wrapper and project files
# COPY mvnw pom.xml ./
# COPY .mvn .mvn  

# # Make Maven wrapper executable
# RUN chmod +x mvnw  

# # Download dependencies and compile the application
# RUN ./mvnw clean package  

# # Copy the full source code and recompile
# COPY . .  
# RUN ./mvnw clean package  

# # Set environment variables (can be overridden at runtime)
# ENV JWT_SECRET=foo  
# ENV SERVER_PORT=8083  

# # Expose the server port
# EXPOSE ${SERVER_PORT}  

# # Run the Spring Boot application
# CMD ["java", "-jar", "target/users-api-0.0.1-SNAPSHOT.jar"]
