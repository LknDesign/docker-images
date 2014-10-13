base
====

This image builds my default environment for NPM / nodejs projects.

This is an "abstract" image and is not suitable to be directly used as a docker container, but as a re-usable Dockerfile base image.

base image
----------

[base](../docker-base/)

tools included
--------------

  - npm
  - git
  - ruby
  - ruby-compass

Volume shared
-------------
  - /app: the place where the application is managed
  - /home: the home of the 'user'

Entrypoint
----------
  - /bin/zsh (from sted/base)
