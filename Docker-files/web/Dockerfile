FROM nginx

LABEL "PROJECT" = "vprofile"
LABEL  "Author" = "Rockson"



RUN rm -rf /etc/nginx/conf.d/default.conf

COPY nginvproapp.conf etc/nginx/conf.d/vproapp.conf
