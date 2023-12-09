FROM python:3.11-alpine as builder
COPY package.json .npmrc pnpm-lock.yaml /tmp/build/
RUN set -x \
  && apk update \
  && apk add nodejs npm git \
  && npm -v \
  && npm i -g pnpm@8.3.1 \
  && cd /tmp/build \
  && pnpm install --prod
