FROM ruby
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y \
		build-essential \
		libpq-dev \
		nodejs \
		sqlite3

#RUN gem install bundler --no-document
#RUN gem install rails --no-document
#RUN gem install rake --no-document

#RUN mkdir -p /opt/app
#WORKDIR /opt/app

# The ONBUILD command adds the instructions to work until the img is used as base of another build
ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# docker build -t ft-rails:on-build . — Build an image from your Dockerfile
# docker build -t ex02 . — Build an image from Dockerfile provided by task
# docker run -it --rm -p 3000:3000 ex02 — Run created image
