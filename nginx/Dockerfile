# Set the base image to Ubuntu
FROM ubuntu

# Install Nginx

# Update the repository
RUN apt-get update

# Install necessary tools
RUN apt-get install -y nano wget dialog net-tools

# Download and Install Nginx
RUN apt-get install -y nginx  

# Remove the default Nginx configuration file
RUN rm -v /etc/nginx/nginx.conf
RUN rm /etc/nginx/sites-enabled/default


# Copy a configuration file from the current directory
ADD ./conf/nginx.conf /etc/nginx/
ADD ./conf/ipsallow.conf /etc/nginx/conf.d/
RUN mkdir /usr/share/nginx/logs/

# Append "daemon off;" to the configuration file

RUN echo "daemon off;" >> /etc/nginx/nginx.conf

#Expose ports
EXPOSE 80

ENTRYPOINT ["/usr/sbin/nginx"]


