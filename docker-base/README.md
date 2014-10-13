base
====

This image builds my default environment based on Debian jessie (8.0)

user
----

The default user 'user' is created, her home is '/home' in group 'sudo' (can launch command without password).

tools included
--------------

  - sudo
  - wget
  - curl
  - zsh

Volume shared
-------------
  - /home: the home of the 'user'

Entrypoint
----------
  - /bin/zsh
