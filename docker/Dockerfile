FROM node:18-slim as nodebuilder

FROM python:3.10-slim-bullseye as builder
COPY package.json .npmrc pnpm-lock.yaml /tmp/build/
COPY --from=nodebuilder /usr/local/bin/node /usr/local/bin/
COPY --from=nodebuilder /usr/local/lib/node_modules/. /usr/local/lib/node_modules/
RUN set -x && \
  ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm && \
  apt update && \
  apt install --no-install-recommends -y libatomic1 && \
  npm i -g pnpm@8.3.1 && \
  cd /tmp/build && \
  pnpm --registry https://registry.npmmirror.com install --prod
