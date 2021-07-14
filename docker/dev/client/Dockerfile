# Image
FROM node:current-alpine3.11

# Set up work directory
WORKDIR /var/www/client

# Configure host
ENV HOST 0.0.0.0


RUN apt update && \
	apt upgrade && \
	apt --no-cache add tar curl tini \
    && apt --no-cache add --virtual devs gcc make python wget unzip ca-certificates \
	&& apt del devs gcc make python wget unzip ca-certificates \
	&& npm cache clean \
	&& rm -rf /tmp/npm* \

  cd /var/www/client; \
  wget --no-check-certificate -O master.zip https://github.com/familytree365/frontend/archive/master.zip; \
  unzip master.zip; \
  cp frontend-master/package.json .
  cp frontend-master/* .
# Init command
CMD ["sh", "-c", "yarn install && yarn dev"]