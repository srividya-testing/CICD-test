# Use Node.js LTS base image
FROM node:18

# Set working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json first
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the source code
COPY . .

# Expose port 3000
EXPOSE 3000

# Default command
CMD ["npm", "start"]
