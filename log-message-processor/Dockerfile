# Use official Python image as base
FROM python:3.11-slim

# Set working directory inside the container
WORKDIR /app

# Copy requirements file first (for better caching)
COPY requirements.txt .

# Install system dependencies required for building Python packages
RUN apt-get update && apt-get install -y \
    gcc \
    python3-dev \
    libffi-dev \
    build-essential \
    libssl-dev \
    python3-pip \
    python3-setuptools \
    python3-wheel \
    flex \
    bison \
    && apt-get clean

# Upgrade pip first to avoid old dependencies issues
RUN pip install --upgrade pip setuptools wheel

# Install thriftpy2 before installing requirements
RUN pip install --no-cache-dir thriftpy2

# Install requirements
RUN pip install --no-cache-dir -r requirements.txt

RUN pip3 install -r requirements.txt
# Copy the rest of the application
COPY . .

# Expose required ports
EXPOSE 8000

# Set environment variables
# ENV REDIS_HOST=redis \
#     REDIS_PORT=6379 \
#     REDIS_CHANNEL=log_channel

# Run the application
CMD ["python3", "main.py"]









# # Use a base image with Python
# FROM python:3.12  

# # Set the working directory inside the container
# WORKDIR /app  

# # Copy the requirements file first (for caching efficiency)
# COPY requirements.txt .  

# # Install dependencies
# RUN pip3 install --no-cache-dir -r requirements.txt  

# # Copy the entire project into the container
# COPY . .  

# # Set environment variables (default values, can be overridden at runtime)
# ENV REDIS_HOST=127.0.0.1  
# ENV REDIS_PORT=6379  
# ENV REDIS_CHANNEL=log_channel  

# # Expose port (only if necessary, but not required for a Redis consumer)
# EXPOSE 8000  

# # Start the Redis message processor
# CMD ["python3", "main.py"]

