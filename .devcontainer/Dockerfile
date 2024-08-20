# Use an official Python runtime as the base image
FROM python:3.9-slim

# Install necessities
RUN apt-get update && apt-get install -y \
    curl gnupg 

# Install Node.js
RUN curl -fsSL https://deb.nodesource.com/setup_14.x | bash - && \
    apt-get install -y nodejs

# Install MongoDB
RUN curl -fsSL https://www.mongodb.org/static/pgp/server-4.4.asc | apt-key add - && \
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/debian buster/mongodb-org/4.4 main" | tee /etc/apt/sources.list.d/mongodb-org-4.4.list && \
    apt-get update && \
    apt-get install -y mongodb-org

# Set the working directory
WORKDIR /workspace

# Install Python dependencies
RUN pip install --no-cache-dir Flask Django

# Expose the port
EXPOSE 3000