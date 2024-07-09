# Stage 1: Build the React app
FROM node:16 AS build

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application
COPY . .

# Build the React app
RUN npm run build

# Debugging step: List files in /app
RUN ls -la /app

# Stage 2: Serve the React app using Nginx
FROM nginx:alpine

# Copy the built app from the previous stage
COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Ensure the default entrypoint is used
ENTRYPOINT ["nginx"]

# Start Nginx server
CMD ["-g", "daemon off;"]

# Start Nginx server
#CMD ["nginx", "--host", "-g", "daemon off;"]
