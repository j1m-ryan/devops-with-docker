FROM ruby:3.0.0

EXPOSE 3000

WORKDIR /usr/src/app

RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash -

RUN apt install -y nodejs

RUN npm install -g yarn

RUN gem install bundler:2.2.11

COPY . .

RUN bundle install

RUN rails db:migrate RAILS_ENV=production

RUN rake assets:precompile

CMD [ "rails", "s", "-e", "production" ]