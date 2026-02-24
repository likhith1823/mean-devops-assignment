# Use official Node image
FROM node:18

# Create app directory inside container
WORKDIR /app

# Copy package.json first
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy remaining source code
COPY . .

# Expose backend port
EXPOSE 8080

# Start the server
CMD ["node", "server.js"]
