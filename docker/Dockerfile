FROM python:3.11-alpine3.18 as builder

RUN apk add --no-cache file nodejs-current npm

RUN which node

RUN file $(which node)

RUN ldd $(which node)

RUN node -v

RUN NODE_DEBUG=* timeout 1m node $(which npm) -v
