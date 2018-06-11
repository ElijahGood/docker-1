FROM ruby

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install -y nodejs
RUN gem install rails
RUN gem install bundler
RUN mkdir -p opt/app

ONBUILD WORKDIR /opt/app
ONBUILD ADD . /opt/app

ONBUILD EXPOSE 3000

ONBUILD RUN bundle update && bundle install && rails db:migrate && rails db:seed

# docker build -t test-ex02 .
# git clone https://bitbucket.org/railstutorial/sample_app_4th_ed.git generic
# cd generic
# echo 'FROM ft-rails:on-build\nEXPOSE 3000\nCMD ["rails", "s", "-b", "0.0.0.0", "-p", "3000"]' > Dockerfile
# docker build -t rails .
# docker run -it --rm -p 3000:3000 rails

