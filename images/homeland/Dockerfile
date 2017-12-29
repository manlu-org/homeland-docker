# NAME:     homeland/homeland
FROM homeland/base:latest
MAINTAINER Jason Lee "https://github.com/huacnlee"

ENV RAILS_ENV 'production'


RUN apt-get install -yy libxslt-dev libxml2-dev


RUN useradd ruby -s /bin/bash -m -U &&\
    mkdir -p /var/www &&\
    cd /var/www &&\
    git clone https://github.com/manlu-org/homeland.git
RUN cd /var/www/homeland && bundle install --deployment &&\
    find /var/www/homeland/vendor/bundle -name tmp -type d -exec rm -rf {} + &&\
    chown -R ruby:ruby /var/www

WORKDIR /var/www/homeland
