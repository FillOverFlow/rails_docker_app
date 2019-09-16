FROM ruby:2.6.3-alpine3.10
RUN apk update && apk add build-base vim curl bash tzdata nodejs nodejs-npm postgresql-dev imagemagick yarn git

ENV RAILS_ROOT /app 
WORKDIR $RAILS_ROOT

COPY Gemfile Gemfile.lock package*.json ./
RUN gem install bundler \
  && bundle install \
  && npm install

COPY . .
RUN bundle exec rake assets:precompile

EXPOSE 3000
CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]