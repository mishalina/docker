FROM ruby:2.3.4
MAINTAINER abooster <abooster@stusent.21-school.ru>

# see http://guides.rubyonrails.org/command_line.html#rails-dbconsole
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y nodejs
RUN gem install rails --version 4.2.7

RUN mkdir -p /opt/app
WORKDIR /opt/app

# The ONBUILD command adds the instructions to work until the img is used as base of another build
ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
#docker build -t ft-rails:on-build .
#docker run -it --rm ft-rails:on-build
