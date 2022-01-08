Scalingo Buildpack: Shell
=====================

Run custom commands during the build process.


Description
-----------

This buildpack allows to execute arbitrary commands on the build container during the build process.

Just create the file `.scalingo/compile.sh` in the root directory of your application and write in this file the commands that you want to execute. This file is then ran in *subshell* by the `compile` script of this buildpack. That is, the commands in `.scalingo/run.sh` are executed on the build dyno as they would be part of the `compile` script.

Available build-specific variables are `BUILD_DIR`, `CACHE_DIR`, and `ENV_DIR`.

The initial working directory is the root directory of your application(BUILD_DIR).

Usage
-----

Simply do:

```bash
# Create file '.scalingo/compile.sh' containing bash commands
mkdir .scalingo
echo 'echo "hello world"' >.scalingo/compile.sh

```

You can specify the latest production release of this buildpack for upcoming builds of an existing application:
```bash
scalingo env-set BUILDPACK_URL=https://github.com/pli01/scalingo-buildpack-shell
```


License
-------
Based on https://github.com/weibeld/scalingo-buildpack-run/
Based on https://github.com/niteoweb/heroku-buildpack-shell
