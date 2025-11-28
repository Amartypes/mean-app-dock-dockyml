# Use Node.js LTS version
FROM node:18

# Create app directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies (only production)
RUN npm install --production

# Copy the rest of your backend code
COPY . .

# Expose backend port
EXPOSE 8080

# Start the server
CMD ["node", "server.js"]

