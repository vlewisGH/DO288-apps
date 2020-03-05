# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

# Change port to 8080
EXPOSE 8080

# Lables 
LABEL io.openshift.expose-services="8080:http" \
      io.k8s.description="A basic Appache HTTP Server child image, uses ONBUILD" \
      io.k8s.display-name="Apache HTTP Server" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="apache, httpd"

# RUN instructions to change the oprt number
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

# Permission to allow webserver process to rw files
RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

# Unpriviledged user instruction
USER 1001






