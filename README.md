# heroku-v8js

Custom platform packages of V8Js for Heroku.

See [Heroku documentation](https://github.com/heroku/heroku-buildpack-php/blob/master/support/build/README.md)
for details on what this is all about.

In order to use V8Js on Heroku you can (meanwhile) stick with the normal PHP buildpack.
You just have to set the `HEROKU_PHP_PLATFORM_REPOSITORIES` like so:

```
heroku config:set HEROKU_PHP_PLATFORM_REPOSITORIES="https://heroku-v8js.s3.amazonaws.com/dist-cedar-14-stable/packages.json"
```

This will cause composer to fetch V8Js from "heroku-v8js" S3 bucket which is managed by
[@stesie](https://github.com/stesie/) (current maintainer of V8Js).
