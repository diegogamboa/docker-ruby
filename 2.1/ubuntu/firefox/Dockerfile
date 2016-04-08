FROM revinate/ruby:2.1-ubuntu

# install firefox, xvfb, and other libraries
RUN apt-get update \
    && apt-get install -y --no-install-recommends build-essential git git-core \
       curl wget xvfb firefox sqlite3 unzip scrot zlib1g-dev libssl-dev \
       libreadline-dev libyaml-dev libsqlite3-dev libxml2-dev libxslt1-dev \
       libcurl4-openssl-dev libffi-dev libmysqlclient-dev

# prebuild nokogiri
RUN gem install nokogiri

COPY docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["irb"]
