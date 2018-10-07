FROM maven:latest

# In order to speed up the Docker Build step, After creating the first Image from Maven:latest image, update the Dockerfile to use base image as it will have all the dependencies downloaded. 
# This Command to create Base image `docker -D build -t hello-dropwizard:base -f docker/Dockerfile .`

#FROM hello-dropwizard:base

RUN mkdir -p /opt/hello-dropwizard
ADD . /opt/hello-dropwizard/

RUN cd /opt/hello-dropwizard/ && mvn package
WORKDIR /opt/hello-dropwizard
CMD [ "java", "-jar" , "target/hello-dropwizard-1.0-SNAPSHOT.jar" ,"server" ,"example.yaml"]
