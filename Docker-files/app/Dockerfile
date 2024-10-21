#build image jdk 11
FROM openjdk:11 AS build_image
RUN apt update && apt install maven -y
RUN git clone https://github.com/devopshydclub/vprofile-project 
RUN cd vprofile-project && git checkout docker && mvn install

#build image tomcat
FROM tomcat:9.0-jre11 
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build_image vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]