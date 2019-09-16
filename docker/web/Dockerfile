FROM nginx:1.17.3-alpine

ENV RAILS_ROOT /app

WORKDIR $RAILS_ROOT

COPY public public/

COPY docker/web/nginx.conf /etc/nginx/conf.d/default.conf 

EXPOSE 8080 

CMD [ "nginx","-g","daemon off;" ]