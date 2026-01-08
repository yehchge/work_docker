FROM nginx:latest

ADD nginx.conf /etc/nginx/nginx.conf
ADD sites-enabled/* /etc/nginx/conf.d/
RUN chown -R www-data:www-data /usr/share/nginx/html
RUN chmod -R 755 /usr/share/nginx/html
