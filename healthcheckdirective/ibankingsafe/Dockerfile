FROM ubuntu:20.04
RUN apt update -y
RUN apt install -y openjdk-11-jdk
RUN apt install -y curl
ENV TOMCAT_HOME=/u01/middleware/apache-tomcat-9.0.87/
ENV PATH=$PATH:$TOMCAT_HOME/bin

RUN mkdir -p /u01/middleware
WORKDIR /u01/middleware
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.87/bin/apache-tomcat-9.0.87.tar.gz .
RUN tar -xvzf apache-tomcat-9.0.87.tar.gz
RUN rm -rf apache-tomcat-9.0.87.tar.gz
COPY target/ibankingsafe-1.0.war apache-tomcat-9.0.87/webapps/
COPY run.sh apache-tomcat-9.0.87/bin
RUN chmod 777 apache-tomcat-9.0.87/bin/run.sh

HEALTHCHECK --interval=30s --timeout=30s --start-period=5s  --retries=3 CMD curl --fail https://localhost:8082/account/123/balance

CMD [ "apache-tomcat-9.0.87/bin/run.sh" ]
