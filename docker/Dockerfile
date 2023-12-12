FROM python:3.11-alpine as builder
RUN set -x \
  && apk update \
  && apk add nodejs npm git \
  && node -v \
  && npm -v
