# dockertags

[![Docker Repository on Quay](https://quay.io/repository/wantedly/dockertags/status "Docker Repository on Quay")](https://quay.io/repository/wantedly/dockertags)

`dockertags` retrieves and print available Docker image tag list from image repository.

## How to build and install

```bash
$ go get -d github.com/wantedly/dockertags
$ cd $GOPATH/src/github.com/wantedly/dockertags
$ make
$ make install
```

## Usage

```bash
$ dockertags
Usage:
  dockertags IMAGENAME
```

Provide Docker image name, then available tags of given image will be shown.

```bash
$ dockertags quay.io/wantedly/dockertags
latest
master

$ dockertags mysql/mysql-server
latest
8.0
8.0.0
5.7
5.7.9
...
5.5.42
```

## Supported image registry

- [Quay.io](https://quay.io)
  - To retrieve tags of private image, pass [API access token](http://docs.quay.io/api/) to `QUAYIO_TOKEN` environement variable.
- [Docker Hub](https://hub.docker.com)
  - To retrieve tags of private image, set `DOCKER_USERNAME` and `DOCKER_PASSWORD` for [Docker Hub](hub.docker.com). If they're not set, only tags for public images will be fetched.
- [Amazon ECR](https://aws.amazon.com/ecr/)
  - To retrieve tags of private image, set proper `AWS_PROFILE` and `AWS_REGION` variable in your environment variables. If `AWS_PROFILE` is not set, it will use `AWS_DEFAULT_PROFILE`.

## License
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)
