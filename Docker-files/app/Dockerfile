#choose the right base image and version to build the images
#below is image openjdk, version(tag) 11
FROM openjdk:11 AS Build_aritifact 

#install maven in image to build java artifact
RUN apt update && apt install maven -y

#clone the project 
RUN git clone https://github.com/devopshydclub/vprofile-project.git

#cd to folder, checkout to branch docker and build artifact
RUN cd vprofile-project && git checkout docker && mvn install

FROM tomcat:9-jre11
#label the images
LABEL "Project" = "Vprofile"
LABEL "Author" = "DuongBT"
#remove default file from tomcat images, read the tomcat document in dockerhub image
RUN rm -rf /usr/local/tomcat/webapps/*

#Copy the artifact from image Build_artifact
COPY --from=Build_aritifact vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080

#Run catalina
CMD ["catalina.sh", "run"]