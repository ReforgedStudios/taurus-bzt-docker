FROM cdelaitre/centos-openjdk:8
MAINTAINER Christophe Delaitre <cdelaitre@gmail.com>

### ENV
ENV TOMCAT_VERSION=8.0.26

### TOMCAT
RUN mkdir -p /produits
ADD apache-tomcat-${TOMCAT_VERSION}.tar.gz /produits
RUN mv /produits/apache-tomcat-${TOMCAT_VERSION} /produits/tomcat
WORKDIR /produits/tomcat
COPY tomcat-users.xml /produits/tomcat/conf/
RUN echo "CATALINA_HOME=/produits/tomcat" >> /etc/environment
EXPOSE 8080
ENTRYPOINT ["/produits/tomcat/bin/catalina.sh", "run"]
