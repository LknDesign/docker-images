# This build a NPM / nodejs environment

FROM lkndesign/base
MAINTAINER Sylvain <stedoldi@lkn-design.com>

RUN PATH=/root/fake:$PATH sudo -E apt-get install -qqy --no-install-recommends \
      npm git ruby ruby-compass       \
      ;

# nodejs / npm / bower
RUN sudo update-alternatives --install /usr/bin/node nodejs /usr/bin/nodejs 1 \
      && sudo npm update -g npm    \
      && sudo npm install -g bower \
      ;

RUN sudo apt-get clean && sudo rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME [ "/app", "/home" ]
