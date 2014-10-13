# Environment for project using angular generator
FROM lkndesign/npm
MAINTAINER Sylvain <stedoldi@lkn-design.com>

RUN sudo apt-get update \
  && PATH=/root/fake:$PATH sudo -E apt-get install -qqy --no-install-recommends \
    libpng-dev \
  && sudo npm install -g grunt generator-angular \
  ;

EXPOSE 3000

WORKDIR /app
