FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/moaf92/containerization.git
RUN cd containerization &&  mvn install 

FROM tomcat:9-jre11
LABEL "Project"="docker"
LABEL "Author"="Mo"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE containerization/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
