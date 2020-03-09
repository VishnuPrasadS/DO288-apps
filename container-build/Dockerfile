# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

EXPOSE 8080

LABEL io.openshift.expose-services="8080:http"

LABEL io.k8s.description="A basic HTTP server child image, USES onbuild" \
      io.k8s.displayname="Apache HTTP server" \
      io.k8s.expose-services="8080:http" \
      io.openshift.tags="apache, httpd"

# This stuff is needed to ensure a clean start
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd && chmod -R g=u /var/log/httpd /var/run/httpd

# Run as the root user
USER 1001
