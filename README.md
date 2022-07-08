# Jungsoft Docker image for Python+Playwright in Ubuntu

This docker image was created to allow using Python and Playwright in Ubuntu.

## Usage

`docker pull jungsoft/playwright-python`

This image was built using

`docker build --platform linux/amd64,linux/arm64 . --tag jungsoft/playwright-python:3.8 --tag jungsoft/playwright-python:3.8.13 --push`
