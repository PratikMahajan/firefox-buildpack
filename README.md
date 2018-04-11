Heroku buildpack: Firefox 59.0
================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for [Firefox](http://www.mozilla.org/en-US/firefox/new/). Meant to be used in combination with something like xvfb, for headless operation.

Usage
-----

Example usage:

```shell
$ heroku create --stack cedar --buildpack http://github.com/PratikMahajan/firefox-buildpack.git

# or if your app is already created:
$ heroku config:add BUILDPACK_URL=http://github.com/PratikMahajan/firefox-buildpack.git

$ git push heroku master
```

Note
-----

If you're using [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to include other buildpacks, you should set environment variable by your own to include following paths.

    PATH="/usr/local/bin:/usr/bin:/bin:/app/vendor/firefox"
    LD_LIBRARY_PATH="/usr/local/lib:/usr/lib:/lib:/app/vendor/firefox"
