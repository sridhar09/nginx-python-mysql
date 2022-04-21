FROM nginx:1.13-alpine
COPY conf /etc/nginx/conf.d/default.conf
COPY ssl/nginx-selfsigned.crt /etc/ssl/certs/nginx-selfsigned.crt
COPY ssl/nginx-selfsigned.key /etc/ssl/private/nginx-selfsigned.key
COPY dhparams/dhparam.pem /etc/ssl/certs/dhparam.pem