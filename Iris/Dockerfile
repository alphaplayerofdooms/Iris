# Use an official Ruby runtime as a parent image
FROM ruby:3.0.6

RUN apt-get update -qq && apt-get install -y build-essential libv8-dev

WORKDIR /app

COPY . /

RUN gem install bundler -v 2.4.22

RUN  bundle install

RUN gem install nokogiri -v 1.13.10
RUN gem install rails -v 6.1.7.3

# Expose port 3000 to the outside world
EXPOSE 3000

# Start the Rails server
CMD ["rails", "server", "-b", "0.0.0.0"]