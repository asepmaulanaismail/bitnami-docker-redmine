FROM bitnami/oraclelinux-extras:7-r130
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages ImageMagick bzip2-libs cyrus-sasl-lib expat fontconfig freetype ghostscript glibc imagemagick jbigkit-libs keyutils-libs krb5-libs libICE libSM libX11 libXau libXext libXt libcom_err libcurl libgcc libgomp libidn libjpeg-turbo libselinux libssh2 libstdc++ libtiff libtool-ltdl libuuid libxcb libxml2 libxslt mariadb-libs ncurses-libs nspr nss nss-softokn-freebl nss-util openldap openssl-libs pcre postgresql-libs readline xz-libs zlib
RUN bitnami-pkg install ruby-2.4.4-0 --checksum 8623ed8b7963916ff7f5ecf56c62ce3c144a1d11e56767500d0034c8e4f7e17c
RUN bitnami-pkg install postgresql-client-9.6.10-0 --checksum 8060eeb7977a80dacb9bbcbc9d6081a6c6472d5fcee25e63bab04a1f128b5489
RUN bitnami-pkg install mysql-client-10.1.36-0 --checksum 066d5ea1a684175a9a9709a0d7d1585067324f58bcd8a569d1fd8e61028dc71b
RUN bitnami-pkg install git-2.19.1-0 --checksum a50a849103d0908bb94c4a048622aae0b090af99739309f7f2a093e119e9453e
RUN bitnami-pkg unpack redmine-3.4.6-1 --checksum 1c00bfe523614039b8565c944e95ed4fbb4cff252f47d45bf1e4c84684091ef6

COPY rootfs /
ENV BITNAMI_APP_NAME="redmine" \
    BITNAMI_IMAGE_VERSION="3.4.6-ol-7-r97" \
    PATH="/opt/bitnami/ruby/bin:/opt/bitnami/postgresql/bin:/opt/bitnami/mysql/bin:/opt/bitnami/git/bin:$PATH" \
    REDMINE_DB_MYSQL="mariadb" \
    REDMINE_DB_PASSWORD="" \
    REDMINE_DB_PORT_NUMBER="" \
    REDMINE_DB_POSTGRES="" \
    REDMINE_DB_USERNAME="" \
    REDMINE_EMAIL="user@example.com" \
    REDMINE_LANGUAGE="en" \
    REDMINE_PASSWORD="bitnami1" \
    REDMINE_USERNAME="user" \
    SMTP_HOST="" \
    SMTP_PASSWORD="" \
    SMTP_PORT="" \
    SMTP_TLS="true" \
    SMTP_USER=""

EXPOSE 3000

ENTRYPOINT [ "/app-entrypoint.sh" ]
CMD [ "/run.sh" ]
