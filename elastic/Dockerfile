FROM nginx:1.25.4
RUN mkdir /etc/nginx/sites-available
COPY elk /etc/nginx/conf.d/default.conf
COPY .htpasswd /etc/nginx/.htpasswd

