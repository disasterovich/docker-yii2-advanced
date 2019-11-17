FROM nginx:alpine

RUN mkdir -p /etc/nginx/sites-enabled

#or try ADD
COPY ./sites-enabled /etc/nginx/sites-enabled

#virtual hosts configs
RUN sed -i -e '/include \/etc\/nginx\/conf\.d\/\*\.conf\;/a \ \ \ \ include \/etc\/nginx\/sites\-enabled\/\*;' /etc/nginx/nginx.conf

RUN mkdir -p /var/www

CMD ["nginx", "-g", "daemon off;"]

EXPOSE 80