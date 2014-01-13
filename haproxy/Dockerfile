FROM ubuntu:12.04

MAINTAINER cohesiveft

# make sure everything is up to date - update and upgrade
RUN apt-get update && apt-get upgrade -y

# install haproxy
RUN apt-get install -y haproxy

# move default config out of the way
RUN mv /etc/haproxy/haproxy.cfg /etc/haproxy/default_haproxy.cfg

# upload local haproxy config file
ADD ./haproxy.cfg /etc/haproxy/

# expose port 80
EXPOSE 80

# run haproxy
CMD /usr/sbin/haproxy -f /etc/haproxy/haproxy.cfg

# example usage:
# sudo docker run -d -p 80:80 cohesiveft/haproxy
