# Use a minimal base image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json first (for caching layers)
COPY package.json package-lock.json ./

# Install only production dependencies
RUN npm ci --omit=dev

# Copy application code
COPY . .

# Expose the application port (modify port if needed)
EXPOSE 3003

# Use a non-root user for security
USER node

# Start the application
CMD ["node", "app.js"]
