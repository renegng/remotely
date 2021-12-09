# Official Nginx 1.21 image
FROM nginx:1.21

# Delete the default configuration and copy our custom one
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d