# Step 1: Build the React app
FROM node:18 AS build

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json (if available) from the 'my-react-app' folder
COPY my-react-app/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app from 'my-react-app' folder
COPY my-react-app/ ./

# Build the React app
RUN npm run build

# Step 2: Serve the app with Nginx
FROM nginx:alpine

# Copy the build folder from the previous stage to Nginx's HTML folder
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80 to allow external traffic
EXPOSE 80

# Start Nginx to serve the app
CMD ["nginx", "-g", "daemon off;"]



