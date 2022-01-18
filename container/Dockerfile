FROM node:17.3-slim as base
ENV LANG="C.UTF-8" \
    TZ="Asia/Tokyo"
RUN cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
ARG IMAGE_VERSION
ENV IMAGE_VERSION ${IMAGE_VERSION}

ENV APP_HOME /app
WORKDIR ${APP_HOME}

COPY package.json ./
COPY package-lock.json ./

FROM base as development
ENV NODE_ENV development
RUN npm instal

FROM base as production
ENV NODE_ENV production
RUN npm instal
