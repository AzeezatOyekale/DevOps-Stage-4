FROM python:3.8
WORKDIR /app
COPY requirements.txt .
# First install C dependencies needed for thriftpy2
RUN apt-get update && apt-get install -y gcc python3-dev
# Then install Python requirements
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "main.py"]








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

