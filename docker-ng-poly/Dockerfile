# Environment for project using ng-poly generator
#   https://github.com/dustinspecker/generator-ng-poly
FROM sted/npm
MAINTAINER Sylvain <stedoldi@lkn-design.com>

RUN sudo apt-get update \
  && PATH=/root/fake:$PATH sudo -E apt-get install -qqy --no-install-recommends \
    libpng-dev \
  && sudo npm install -g gulp generator-ng-poly \
  ;

EXPOSE 3000

WORKDIR /app
