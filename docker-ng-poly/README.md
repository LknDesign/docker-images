ng-poly
=======

This image builds my default environment for ng-poly application (https://github.com/dustinspecker/generator-ng-poly)

base image
----------

[npm](../docker-npm/)


use cases
---------

Serve the application:
```sh
docker run -d --name <your-app-name> -d -v /my/local/app/dir/:/app/ -p 3000:3000 lkndesign/ng-poly -c gulp
```

Enter the shell:
```sh
docker run --rm -it -p 3000:3000 -v /my/local/app/dir/:/app/ -v /my/local/home/:/home/ lkndesign/ng-poly
```


tools included
--------------

  - gulp
  - generator-ng-poly

Volume shared
-------------
  - `/app`: the place where the application is managed
  - `/home`: the home of the 'user'

Exposed port
------------
  - 3000: `gulp` serve port


Entrypoint
----------
  - `/bin/zsh` (from [base](../docker-base)), workdir being `/app`
