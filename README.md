Hotswap-docklands
=================

Adam Bien's Docklands with HotswapAgent and DCEVM.

## Motivation:

Allow advanced hotswap support for JVM (dcevm) running in Docker container.

## Quick start:

### Install desired container image

Each folder represents a Dockerfile which can be built by executing the `build.sh` command. 

### Add docker container hotswap support to your project

Copy following files from [reference project](https://github.com/skybber/ping) to your project:

1. [Dockerfile](https://github.com/skybber/ping/blob/master/Dockerfile) 
  * modify name of `ping.war` to `your_project.war`
  * optionally modify parent image name `FROM` to desired container image name
2. [hotswap-agent.properties](https://github.com/skybber/ping/blob/master/src/main/resources/hotswap-agent.properties) to your project's `resources` directory.
3. [buildAndRunDebug.sh](https://github.com/skybber/ping/blob/master/buildAndRunDebug.sh) 
  * rename destination image name from `hotswap-ping` to something else
4. run `buildAndRunDebug.sh`
  * Debug your application attaching your debugger to port `8000`
  * Make some advance code change in your project and build the project. Class changes are automatically promoted to running docker container via debugger. Even if the debugger is not attached, the class changes are promoted via `extra_class_path`, that is used prior standard classpath.

HotswapAgent allows to add a directory prior to webapp path (load webapp resources) using property `webappDir`. For proper functionality of `webappDir` it is necessary to add `-v /var/run/docker.sock:/var/run/docker.sock` to docker command.
