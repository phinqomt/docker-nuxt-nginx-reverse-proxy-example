# Dockerfile
# FROM nginx:latest
# COPY ./docker/nginx/nginx.conf /etc/nginx/conf.d/default.conf

FROM node:lts-alpine

# create destination directory
RUN mkdir -p /usr/src/nuxt-app
WORKDIR /usr/src/nuxt-app

# update and install dependency
# RUN apk update && apk upgrade
# RUN apk add git

COPY . /usr/src/nuxt-app/

RUN npm install

#RUN npm run dev
RUN npm run build

RUN npm run generate

EXPOSE 3002

ENV NUXT_HOST=0.0.0.0
ENV NUXT_PORT=3002

CMD ["npm", "start" ]