# Use Node 20-alpine as base image (matches package.json engines requirement)
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Copy package files first for better layer caching
COPY package*.json ./

# Install dependencies 
# Note: Using --strict-ssl=false as workaround for SSL issues in CI environments
RUN npm install --strict-ssl=false

# Copy all project files
COPY . .

# Expose Vite's default development port
EXPOSE 5173

# Run Vite dev server (server.host configured in vite.config.js)
CMD ["npm", "run", "dev"]
