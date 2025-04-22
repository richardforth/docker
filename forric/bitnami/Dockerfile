FROM bitnami/apache:latest
USER root
RUN install_packages curl procps net-tools perl 
COPY httpd-mpm.conf /opt/bitnami/apache/conf/extra/httpd-mpm.conf
