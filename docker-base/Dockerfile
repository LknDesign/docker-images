# This build a minimal base environment
FROM debian:jessie
MAINTAINER Sylvain <stedoldi@lkn-design.com>

# Keep upstart from complaining 
RUN dpkg-divert --local --rename --add /sbin/initctl \
      && ln -sf /bin/true /sbin/initctl

# Let the conatiner know that there is no tty 
ENV DEBIAN_FRONTEND noninteractive

RUN mkdir /root/fake                                  \
      && ln -s /bin/true /root/fake/initctl           \
      && ln -s /bin/true /root/fake/invoke-rc         \
      && ln -s /bin/true /root/fake/restart           \
      && ln -s /bin/true /root/fake/start             \
      && ln -s /bin/true /root/fake/stop              \
      && ln -s /bin/true /root/fake/start-stop-daemon \
      && ln -s /bin/true /root/fake/service           \
      ;

RUN apt-get update \
      && PATH=/root/fake:$PATH apt-get install -qqy --no-install-recommends \
        locales \
      ;

RUN dpkg-reconfigure locales \
      && locale-gen C.UTF-8  \
      && /usr/sbin/update-locale LANG=C.UTF-8 \
      ;

ENV LC_ALL C.UTF-8
RUN echo LANG="en_US.UTF-8" > /etc/default/locale;

RUN useradd --home-dir /home --groups sudo user && chown user:user /home




RUN PATH=/root/fake:$PATH apt-get install -qqy --no-install-recommends \
      sudo wget curl zsh                 \
      ;

# allow sudo without password
RUN sed -ie 's/%sudo\sALL=(ALL:ALL)\sALL/%sudo\tALL=(ALL) NOPASSWD: ALL/' /etc/sudoers



# Clean up APT when done.
RUN apt-get clean && rm -rf /tmp/* /var/tmp/*

VOLUME [ "/home" ]
ENV HOME /home
USER user

ENTRYPOINT [ "/bin/zsh" ]

