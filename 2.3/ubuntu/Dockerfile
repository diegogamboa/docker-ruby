FROM ubuntu:trusty

RUN apt-get update \
    && apt-get install -y --no-install-recommends software-properties-common \
    && add-apt-repository -y ppa:brightbox/ruby-ng

RUN apt-get update \
    && apt-get install -y --no-install-recommends ruby2.3 ruby2.3-dev

CMD [ "irb" ]
