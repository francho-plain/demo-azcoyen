# Use Node.js LTS image as base
FROM node:22-alpine

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy project files
COPY . .

# Expose port 5173 for Vite development server
EXPOSE 5173

# Run Vite development server
CMD ["npm", "run", "dev"]
