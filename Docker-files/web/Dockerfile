FROM nginx
LABEL "Project"="docker"
LABEL "Author"="Mo"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf