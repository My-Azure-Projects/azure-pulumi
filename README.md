# Azure + Pulumi

![Build](https://img.shields.io/docker/cloud/build/scottam/az-pulumi)
![Docker Pulls](https://img.shields.io/docker/pulls/scottam/az-pulumi)
![MIT Licence](https://img.shields.io/github/license/scott-the-programmer/az-pulumi)

This repository contains the dockerfile to create an image with [Pulumi](https://www.pulumi.com/) and the [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest) installed

The main use for this is to ready-bake the installation so that we can run our Pulumi projects against Azure

Currently, this image is hosted on [Dockerhub](https://hub.docker.com/repository/docker/scottam/az-pulumi)

## Prerequisites

* [Docker](https://docs.docker.com/get-docker/)

## How to build image

```bash
docker build .
```

## Example of usage

Here's an example dockerfile that uses the image

```dockerfile
FROM scottam/az-pulumi:latest

COPY . .

CMD "az login --service-principal -u "$ARM_CLIENT_ID" --password "$ARM_CLIENT_SECRET" --tenant "$ARM_TENANT_ID" && \
 pulumi version"
```

## Exploring the contents of the image

Open it up! Take a look

```bash
docker run -it scottam/az-pulumi:latest bash
``` 
