#ARG BUILD_FROM="alpine:latest"
ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

# Copy data for add-on
COPY run.sh /
COPY js /js

WORKDIR /

# Install requirements for add-on
RUN apk add --no-cache jq
RUN apk add --no-cache npm
#RUN apk add --no-cache g++
RUN apk add --no-cache make
RUN apk add --no-cache gcc

RUN apk add --no-cache python3
RUN apk add --no-cache linux-headers
RUN apk add --no-cache udev

RUN npm init -f

COPY package.json /
RUN npm install mqtt


#RUN npm install mqtt
#RUN npm install serialport --build-from-source=serialport 
# RUN npm install serialport --unsafe-perm --build-from-source=serialport

RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
