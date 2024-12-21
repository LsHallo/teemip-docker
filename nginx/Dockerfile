FROM nginx:stable

ENV TEEMIP_CONTAINER_NAME=teemip

COPY teemip.conf.template /etc/nginx/templates/teemip.conf.template
RUN rm /etc/nginx/conf.d/default.conf
