FROM ubuntu:12.04

MAINTAINER cohesiveft

# add universe repository to /etc/apt/sources.list
# we need it for nginx
RUN sed -i s/main/'main universe'/ /etc/apt/sources.list

# make sure everything is up to date - update and upgrade
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y nginx

# Remove the default Nginx configuration file
RUN rm -v /etc/nginx/nginx.conf

# Copy a configuration file from the current directory
ADD ./nginx.conf /etc/nginx/
ADD ./ssl.key /etc/nginx/ssl/
ADD ./ssl.crt /etc/nginx/ssl/

# Create empty directory for logs
RUN mkdir -p /etc/nginx/logs

# Expose ports
EXPOSE 443

# Set the default command to execute
# when creating a new container
CMD service nginx start

# Example runline:
# sudo docker run -d -p 443:443 cohesiveft/nginxssl
