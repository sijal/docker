FROM ubuntu:24.04
ARG MYSQL_PASSWORD=mysql@007
RUN echo $MYSQL_PASSWORD > ~/mysqlconf
CMD ["/bin/bash", "-c", "cat ~/mysqlconf"]