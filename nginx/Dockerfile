FROM nginx:1.8

MAINTAINER Mathias Grimm <mathiasgrimm@gmail.com>

ADD nginx.conf /etc/nginx/

# Using a 1000 years certificate... should work for some time
COPY ssl/* /etc/nginx/ssl/

COPY sites-enabled/*.conf /etc/nginx/sites-enabled/

RUN mkdir -p /var/www/html

COPY ./index.htm /var/www/html/index.htm

RUN echo "export TERM=xterm-256color">> ~/.bashrc

EXPOSE 80 443

CMD ["nginx"]