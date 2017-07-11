# Set the base image to Ubuntu
FROM ubuntu

# Update the repository
RUN apt-get update

# Install necessary tools
RUN apt-get install -y nano wget dialog net-tools

# Copy a configuration file from the current directory
RUN mkdir /etc/oauth
COPY ./oauth2_proxy /etc/oauth/
COPY ./oauth2_proxy.cfg /etc/oauth/
EXPOSE 4190

CMD ["/etc/oauth/oauth2_proxy","-config=/etc/oauth/oauth2_proxy.cfg"]


