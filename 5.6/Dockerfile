FROM openshift/php-56-centos7

# This image provides an Apache+PHP environment for running Symfony
# applications.

MAINTAINER puzzle.ch <philipona@puzzle.ch>


LABEL io.k8s.description="Platform for building and running PHP 5.6 applications" \
      io.k8s.display-name="Apache 2.4 with PHP 5.6" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="builder,php,php56,rh-php56"


# update scripts
COPY ./s2i/bin/ $STI_SCRIPTS_PATH

# Each language image can have 'contrib' a directory with extra files needed to
# run and build the applications.
COPY ./contrib/ /opt/app-root

USER root

# overwrite php.ini
RUN cp -a /opt/app-root/etc/php.ini.template /etc/opt/rh/rh-php56/php.ini

USER 1001

