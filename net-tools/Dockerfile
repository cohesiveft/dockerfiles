FROM ubuntu:12.04

MAINTAINER cohesiveft

# add universe repository to /etc/apt/sources.list
# we need it for iftop etc.
RUN sed -i s/main/'main universe'/ /etc/apt/sources.list

# make sure everything is up to date - update and upgrade
RUN apt-get update && apt-get upgrade -y

# Install net tools and SSH so that they can be used
RUN apt-get install -y net-tools sysstat iftop tcpstat hping3 nethogs openssh-server

# Add keyfile for SSH access
ADD ./authorized_keys /root/.ssh/

# Ensure correct permissions for root/.ssh
RUN chmod 700 /root/.ssh && chmod 600 /root/.ssh/authorized_keys && chown -R root /root/.ssh

# Expose SSH port
EXPOSE 22

# Run SSH daemon
CMD /usr/sbin/sshd -D

# Example runline:
# sudo docker run -d cohesiveft/net-tools
