#ARG BUILD_FROM=”alpine:latest”
ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

COPY run.sh /
COPY js /js

RUN apk add --no-cache jq npm make gcc g++ python3 linux-headers udev

WORKDIR /share/navien
COPY package.json /
RUN npm install

RUN chmod a+x /run.sh

CMD [ “/run.sh” ]

