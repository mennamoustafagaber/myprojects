# Use Ubuntu as the base image
FROM ubuntu:latest

# Update the package list and install Nginx
RUN apt-get update && apt-get install -y nginx && rm -rf /var/lib/apt/lists/*

# Configure Nginx to listen on port 8085
RUN sed -i 's/listen 80 default_server;/listen 8085 default_server;/' /etc/nginx/sites-available/default && \
    sed -i 's/listen \[::\]:80 default_server;/listen \[::\]:8085 default_server;/' /etc/nginx/sites-available/default

# Ensure the root path is correctly set for the index.html file
RUN sed -i 's|root /var/www/html;|root /usr/share/nginx/html;|' /etc/nginx/sites-available/default

# Create the custom index.html file with a welcome message
RUN echo '<!DOCTYPE html><html><head><title>Welcome</title></head><body><h1>Welcome to DevOps World on Port 8085!</h1></body></html>' > /usr/share/nginx/html/index.html

# Expose port 8085
EXPOSE 8085

# Start Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]

