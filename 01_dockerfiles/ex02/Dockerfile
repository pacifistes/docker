#  docker build -t ft-rails:on-build .
#  docker build -t ft-rails:run -f Dockerfile-fils .
#  	docker run -it -p 3000:3000 ft-rails:run
FROM ruby

# Mise à jour des outils de développement
RUN apt-get -y update && apt-get -y upgrade 

# Installe Node.js et git
RUN apt-get install -y nodejs git


# Install bundler
RUN gem install bundler

COPY ./app /opt/app

WORKDIR /opt/app

# Installe Rails
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate && rake db:setup