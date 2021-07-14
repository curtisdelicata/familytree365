# Image
FROM nginx:alpine

WORKDIR /var/www

# Add config
COPY default.conf /etc/nginx/conf.d/default.conf

RUN apt update && \
	apt upgrade && \
	apt --no-cache add tar curl tini \
    && apt --no-cache add --virtual devs gcc make python wget unzip ca-certificates \
	&& apt del devs gcc make python wget unzip ca-certificates \
	&& npm cache clean \
	&& rm -rf /tmp/npm* \

  cd /var/www; \
  wget --no-check-certificate -O master.zip https://github.com/familytree365/backend/archive/master.zip; \
  unzip master.zip;\
  cp backend-master/* ./