FROM nginx:latest
MAINTAINER Mr. Luigiketter
LABEL version="1.0"
COPY ./hello.c /hello.c
COPY ./run.sh /run.sh
COPY ./nginx.conf /etc/nginx/nginx.conf

RUN \
touch /var/run/nginx.pid && \
chown -R nginx:nginx /var/run/nginx.pid && \
chown -R nginx:nginx /var/log/nginx && \
chown -R nginx:nginx /var/cache/nginx && \
apt-get update && \
apt-get install -y gcc && \
apt-get install -y libfcgi-dev && \
apt-get install -y spawn-fcgi && \
rm -rf /var/lib/apt/lists && \
gcc /hello.c -lpthread -lfcgi -o hello && \
chmod +x /run.sh

HEALTHCHECK NONE
ENTRYPOINT ["/run.sh"]
