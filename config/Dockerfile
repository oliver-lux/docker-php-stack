FROM webdevops/php-nginx:8.3-alpine

# Docs:
# https://dockerfile.readthedocs.io/en/latest/content/DockerImages/dockerfiles/php-nginx.html

COPY ./nginx/* /opt/docker/etc/nginx/vhost.common.d

RUN mkdir -p /app
WORKDIR /app
