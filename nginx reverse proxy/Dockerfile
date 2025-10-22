# Use the official Nginx image as the base
FROM nginx:stable-alpine

# Remove the default Nginx configuration file
# This prevents conflicts with our custom configuration
RUN rm /etc/nginx/conf.d/default.conf

# Copy the custom Nginx configuration file into the container
# We assume the custom file is named 'nginx.conf' and is in the same directory
COPY nginx.conf /etc/nginx/conf.d/

# Expose port 80 (standard HTTP)
EXPOSE 80

# The Nginx image already has a CMD defined to start the server,
# so we don't need to explicitly define one here.