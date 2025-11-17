# Use Node.js 18 (or your Jenkins-configured version)
FROM node:18

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json first
COPY package*.json ./

# Force install PostCSS to fix compatibility issues
RUN npm install postcss@8.4.21 postcss-safe-parser@6.0.0 --legacy-peer-deps

# Install all other dependencies
RUN npm install --legacy-peer-deps

# Copy the rest of the project files
COPY . .

# Expose the application port
EXPOSE 3000

# Set environment variables
ENV NODE_OPTIONS=--openssl-legacy-provider
ENV PORT=3000

# Start the application
CMD ["npm", "start"]
