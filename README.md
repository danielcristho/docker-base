# Docker Base

![Push to DockerHub](https://github.com/danielcristho/docker-base/actions/workflows/push-to-dockerhub.yml/badge.svg)

Build Docker Image to Run on Multiple Platforms.

## How to use

Pull from [Dockerhub](https://hub.docker.com/repositories/danielcristh0).

```bash
docker pull danielcristh0/base-os:tagname
```

Build locally using buildx.

```bash
git clone https://github.com/danielcristho/docker-base.git && cd docker-base
cd <os_directory>
docker buildx create --use --name <buildx_name>
docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7,linux/arm/v8,linux/arm64/v8
```
