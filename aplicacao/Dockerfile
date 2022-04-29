FROM ruby:3.0.0

RUN apt-get update && apt-get install -y build-essential libpq-dev nodejs

WORKDIR /home/gces

COPY Gemfile /home/gces
COPY Gemfile.lock /home/gces

RUN gem install bundler && bundle install

COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]

COPY . /home/gces
EXPOSE 3000