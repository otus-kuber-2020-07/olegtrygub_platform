FROM nginx:stable

RUN sed -i "0,/usr\\/share\\/nginx\\/html/s/usr\\/share\\/nginx\\/html/app/" /etc/nginx/conf.d/default.conf \
    && sed -i s/80/8000/ /etc/nginx/conf.d/default.conf 

RUN usermod -u 1001 nginx \
    && groupmod -g 1001 nginx
    