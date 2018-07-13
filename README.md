# MaSpeng PHAR-Loader
[![CircleCI](https://circleci.com/gh/MaSpeng/docker-hub-phar-loader/tree/master.svg?style=svg)](https://circleci.com/gh/MaSpeng/docker-hub-travis-cli/tree/master) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/35ac4c551c844b7f9b485bbef0bfc630)](https://www.codacy.com/app/marco.spengler/docker-hub-phar-loader?utm_source=github.com&utm_medium=referral&utm_content=MaSpeng/docker-hub-phar-loader&utm_campaign=Badge_Grade)

This docker image includes the [MaSpeng PHAR-loader](https://github.com/MaSpeng/php-phar-loader) for downloading, caching and verifying PHP archives.

## Supported tags and respective Dockerfile links
* `0.1`, `latest` [(0.1/Dockerfile)](https://github.com/maspeng/docker-hub-phar-loader/blob/master/1.0/Dockerfile)

## How to use this image
To use the `PHAR-Loader` you can do the following.

```bash
$ docker run \
    --rm \
    --interactive \
    --tty \
    --workdir /app \
    --volume "$(pwd)":/app \
    maspeng/phar-loader phar:download https://url.to.phar output-file-name.phar
```

You can use any of the PHAR-loader commands

```bash
$ docker run \
    --rm \
    --interactive \
    --tty \
    --workdir /app \
    --volume "$(pwd)":/app \
    maspeng/phar-loader --help
```

You can mount the PHAR-Loader home directory from your host inside the Container to share caching and configuration files:

```bash
$ docker run \
    --rm \
    --interactive \
    --tty \
    --workdir /app \
    --volume ~/.phar-loader:/root/.phar-loader \
    --volume "$(pwd)":/app \
    maspeng/phar-loader
```

## Environments

To override the home directory of the PHAR-Loader you might set the `PHAR_LOADER_HOME` environment:

```bash
$ docker run \
    --rm \
    --interactive \
    --tty \
    --env PHAR_LOADER_HOME=/tmp/.phar-loader \
    --workdir /app \
    --volume ~/.phar-loader:/tmp/.phar-loader \
    --volume "$(pwd)":/app \
    maspeng/phar-loader
```

## Quick reference
* **Where to get help:**
[the Docker Community Forums](https://forums.docker.com), [the Docker Community Slack](https://blog.docker.com/2016/11/introducing-docker-community-directory-docker-community-slack), or [Stack Overflow](https://stackoverflow.com/search?tab=newest&q=docker)

* **Where to file issues:**
https://github.com/maspeng/docker-hub-phar-loader/issues

* **Maintained by:**
[MaSpeng](https://github.com/MaSpeng)

* **Source of this description:**
[Repository README.md](https://github.com/maspeng/docker-hub-phar-loader/blob/master/README.md)
