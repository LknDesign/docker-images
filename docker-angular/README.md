angular
=======

*Consider using [ng-poly](../docker-ng-poly) image instead of this one.*

base image
----------

[npm](../docker-npm/)


use cases
---------

Serve the application:
```sh
docker run -d --name <your-app-name> -d -v /my/local/app/dir/:/app/ -p 3000:3000 lkndesign/angular -c grunt serve
```

Enter the shell:
```sh
docker run --rm -it -p 3000:3000 -v /my/local/app/dir/:/app/ -v /my/local/home/:/home/ lkndesign/angular
```


tools included
--------------

  - grunt
  - generator-angular

Volume shared
-------------
  - `/app`: the place where the application is managed
  - `/home`: the home of the 'user'

Exposed port
------------
  - 3000: `grunt` serve port


Entrypoint
----------
  - `/bin/zsh` (from [base](../docker-base)), workdir being `/app`

Default build command
---------------------

```
docker build --tag lkndesign/angular .
```

