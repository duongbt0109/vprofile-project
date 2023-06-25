#use nginx base image, default version
FROM nginx

#Label the image
LABEL "Project" = "Vprofile"
LABEL "Author" = "DuongBT"

#remove default nginx config
RUN rm -rf /etc/nginx/conf.d/default.conf

#replace with own config
COPY nginvproapp.conf /etc/nginx/conf.d/default.conf
