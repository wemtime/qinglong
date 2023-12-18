FROM python:3.11-alpine as builder

RUN sed -i 's/v3.19\/community/v3.18\/community/g' /etc/apk/repositories
RUN apk add --no-cache file nodejs npm

RUN which node

RUN file $(which node)

RUN ldd $(which node)

RUN node -v

RUN NODE_DEBUG=* timeout 1m node $(which npm) -v
