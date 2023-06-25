#using base image mysql, version 8.0.33
FROM mysql:8.0.33 

#Label the image
LABEL "Project" = "Vprofile"
LABEL "Author" = "DuongBT"

#set mysql info
#find in document of mysql images in dockerhub
ENV MYSQL_ROOT_PASSWORD="Admin123"
ENV MYSQL_DATABASE="accounts"

#copy backup.sql file to image in directory /docker-entrypoint-initdb.d/ to execute when start container
#read on mysql images in dockerhub: Initializing a fresh instance 
COPY db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql

