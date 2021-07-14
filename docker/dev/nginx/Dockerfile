# Image
FROM nginx:alpine

# Add config
COPY default.conf /etc/nginx/conf.d/default.conf

RUN apk update && \
	apk upgrade && \
	apk --no-cache add tar curl tini \
    && apk --no-cache add --virtual devs gcc make python wget unzip ca-certificates \
	&& apk del devs gcc make python wget unzip ca-certificates \
	&& npm cache clean \
	&& rm -rf /tmp/npm*
  
  GIT_URL="https://github.com/familytree365/backend/archive/master.zip"; \
  unzip master.zip; \
