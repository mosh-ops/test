# Use the official Nginx image as the base
FROM nginx:stable-alpine

# Remove the default Nginx configuration
RUN rm /etc/nginx/conf.d/default.conf

# Copy the custom Nginx configuration file into the container
# This sets Nginx to listen on port 8080
COPY nginx.conf /etc/nginx/conf.d/

# Copy your custom HTML file to the web root directory
COPY index.html /usr/share/nginx/html/index.html

# Expose port 8080 (optional but good practice)
EXPOSE 8070

# The Nginx base image already defines the CMD to start the server.