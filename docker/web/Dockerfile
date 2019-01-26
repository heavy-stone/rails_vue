FROM ruby:2.5.1

# ENV LANG ja_JP.UTF-8
ENV LANG C.UTF-8

RUN apt-get update -qq && \
    apt-get install -y nodejs \
                       mysql-client \
                       postgresql-client \
                       sqlite3 \
                       --no-install-recommends && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
    # ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN mkdir /my_app
WORKDIR /my_app
COPY ./Gemfile Gemfile
COPY ./Gemfile.lock Gemfile.lock
RUN bundle install -j3
