FROM ruby:latest

RUN apt-get update && apt-get upgrade -y
RUN apt-get install nodejs -y
RUN gem install rails bundler

MAINTAINER abooster 

# Create application
ONBUILD WORKDIR /opt
ONBUILD RUN rails new app

ONBUILD WORKDIR /opt/app
# install staff
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# build image
# docker build -t ft-rails:on-build ft-rails
