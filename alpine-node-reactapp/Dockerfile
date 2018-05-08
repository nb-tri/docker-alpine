FROM node:8.11-alpine
LABEL maintainer="nguyenbatri84@gmail.com"

WORKDIR /usr/src/app

ARG REACT_APP_API_LINK
ARG REACT_APP_ID

ENV NPM_CONFIG_LOGLEVEL warn

RUN apk add --update nginx && rm -rf /var/cache/apk/*

RUN mkdir -p /tmp/nginx/client-body

RUN ln -sf /dev/stdout /var/log/nginx/access.log && \
    ln -sf /dev/stderr /var/log/nginx/error.log

COPY nginx/nginx.conf /etc/nginx/nginx.conf
COPY nginx/default.conf /etc/nginx/conf.d/default.conf

COPY . .

RUN npm install \
    && npm prune \
    && npm dedupe

EXPOSE 80

CMD REACT_APP_API_LINK=`echo $REACT_APP_API_LINK` REACT_APP_ID=`echo $REACT_APP_ID` npm run build --production \
    && nginx -g 'daemon off;'