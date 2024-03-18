FROM ubuntu:24.04
ARG JAVA_PKG_NAME
RUN apt update -y
RUN apt install -y $JAVA_PKG_NAME
CMD ["/bin/bash", "-c", "java -version"]