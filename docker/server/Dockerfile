FROM ubuntu:18.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get install -y \
        build-essential \
        curl \
        nano \
	nginx

RUN touch /var/log/nginx/tls-access.log

RUN openssl req -x509 -nodes -days 365 -new -newkey rsa:2048 \
        -keyout /etc/nginx/tls_server.key \
        -out /etc/nginx/tls_server.pem \
        -subj '/CN=tls.example.com'

WORKDIR /app

COPY src /app/src
COPY conf/nginx/sites-available/mysite /etc/nginx/sites-available

RUN ln -s /etc/nginx/sites-available/mysite /etc/nginx/sites-enabled/
    
RUN service nginx restart

EXPOSE 80
EXPOSE 443

CMD ["tail", "-f", "/dev/null"]
