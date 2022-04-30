FROM ruby:3.0.0
RUN apt-get update -qq && apt-get install -y nodejs postgresql-client
WORKDIR /aplicacao
COPY Gemfile /aplicacao/Gemfile
COPY Gemfile.lock /aplicacao/Gemfile.lock
RUN bundle install

COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3000

CMD [ "bundle", "exec", "puma", "-C", "config/puma.rb" ]