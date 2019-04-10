FROM ubuntu:trusty

RUN apt-get update \
    && apt-get install -y --no-install-recommends software-properties-common \
    && add-apt-repository -y ppa:brightbox/ruby-ng

RUN apt-get update \
    && apt-get install -y --no-install-recommends ruby2.6 ruby2.6-dev

RUN gem install bundler

CMD [ "irb" ]
