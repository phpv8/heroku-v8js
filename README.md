# heroku-v8js

Custom platform packages of V8Js for Heroku.

See [Heroku documentation](https://github.com/heroku/heroku-buildpack-php/blob/master/support/build/README.md)
for details on what this is all about.

## Usage

In order to use V8Js on Heroku you can (meanwhile) stick with the normal PHP buildpack.
You just have to set the `HEROKU_PHP_PLATFORM_REPOSITORIES` environment variable on your app,
depending on the stack you've chosen.

This will cause Heroku to fetch V8Js from "heroku-v8js" S3 bucket which is managed by
[@stesie](https://github.com/stesie/) (current maintainer of V8Js).

### Configuration via Heroku Web Frontend

Within Heroku portal, choose your app and go to the Settings tab.  In the section labeled
Info you'll see which stack is currently activated, this should be either *heroku-16* or *cedar-14*.

Then click the button *Reveal Config Vars* from the Config Variables section, add a new record
with key *HEROKU_PHP_PLATFORM_REPOSITORIES* and

* for heroku-16 stack: https://heroku-v8js.s3.amazonaws.com/dist-heroku-16-stable/packages.json as value
* for cedar-14 stack: https://heroku-v8js.s3.amazonaws.com/dist-cedar-14-stable/packages.json

### Configuration via Heroku CLI

To find out which stack is currently active, use `heroku apps:info`.

Then if you're using the heroku-16 stack:

```
heroku config:set HEROKU_PHP_PLATFORM_REPOSITORIES="https://heroku-v8js.s3.amazonaws.com/dist-heroku-16-stable/packages.json"
```

Otherwise on cedar-14 type this:

```
heroku config:set HEROKU_PHP_PLATFORM_REPOSITORIES="https://heroku-v8js.s3.amazonaws.com/dist-cedar-14-stable/packages.json"
```
