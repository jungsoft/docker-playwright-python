# Jungsoft Docker Buildx

This docker image was created to allow creating docker images in multiple platforms, on a easily replaceable manner.

## Usage

`docker pull jungsoft/docker-buildx`

To build multi-platform images, run from inside the docker image:

`docker build --platform linux/amd64,linux/arm64,linux/arm/v7 "." --tag tag`

### Example GitLab-CI usage:

```
build:
  stage: build
  image: jungsoft/docker-buildx:stable
  services:
    - docker:dind
  before_script:
    - docker login -u gitlab-ci-token -p $CI_JOB_TOKEN $CI_REGISTRY
  script:
    - docker build --platform linux/amd64,linux/arm64,linux/arm/v7 "." --tag $CONTAINER_CURRENT_IMAGE --push
```

## Build
This image was built using

`docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 . -t jungsoft/docker-buildx:stable --push`
