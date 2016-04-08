FROM revinate/ruby:2.1-ubuntu

# add chrome repository
RUN apt-get update \
    && apt-get install -y --no-install-recommends wget \
    && wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
    && echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list

# install chrome, xvfb, and other libraries
RUN apt-get update \
    && apt-get install -y build-essential git git-core curl sqlite3 xvfb unzip \
       google-chrome-stable zlib1g-dev libssl-dev libreadline-dev libyaml-dev \
       libsqlite3-dev libxml2-dev libxslt1-dev libcurl4-openssl-dev libffi-dev \
       libmysqlclient-dev gtk2-engines-pixbuf xfonts-base xfonts-cyrillic \
       xfonts-100dpi xfonts-75dpi xfonts-scalable scrot

# install chrome driver
RUN wget -O /tmp/chromedriver.zip http://chromedriver.storage.googleapis.com/2.21/chromedriver_linux64.zip \
    && unzip /tmp/chromedriver.zip chromedriver -d /usr/bin/ \
    && chmod ugo+rx /usr/bin/chromedriver

# prebuild nokogiri
RUN gem install nokogiri

COPY docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["irb"]
