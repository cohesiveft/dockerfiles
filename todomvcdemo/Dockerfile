FROM ubuntu:12.04

MAINTAINER cpswan

# add universe repository to /etc/apt/sources.list
# we need it for rubygems
RUN sed -i s/main/'main universe'/ /etc/apt/sources.list

# make sure everything is up to date - update 
RUN apt-get update

# install rubygems, MySQL unzip
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y rubygems libsqlite3-dev unzip

# install gems
RUN gem install sinatra sinatra-contrib data_mapper dm-sqlite-adapter --no-rdoc --no-ri

# copy and install sinatra-ToDoMVC application
ADD https://github.com/cpswan/sinatra-ToDoMVC/archive/sqlite.zip /opt/sinatra-ToDoMVC.zip
RUN cd /opt && unzip /opt/sinatra-ToDoMVC.zip

# default port for Sinatra is 4567
EXPOSE 4567

# run the ToDoMVC app
CMD /usr/bin/ruby /opt/sinatra-ToDoMVC-sqlite/app.rb

# example usage:
# sudo docker run -d -p 4567:4567 cohesiveft/todomvcdemo
