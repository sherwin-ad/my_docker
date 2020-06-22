FROM centos:7
# Upgrade and install base packages
RUN yum update -y \
    && yum install -y epel-release yum-utils \
    && yum -y install nginx \
    && yum -y install https://rpms.remirepo.net/enterprise/remi-release-7.rpm \
    && yum-config-manager --enable remi-php74 \
    && yum -y install php-fpm php-cli php-mysqlnd php-soap php-xml php-zip php-json php-mcrypt php-mbstring php-zip php-gd \
    yum clean all

VOLUME /var/www/html /var/log/nginx /var/log/php-fpm /var/lib/php-fpm

COPY ./conf/default.conf /etc/nginx/conf.d/default.conf
COPY ./conf/www.conf /etc/php-fpm.d/www.conf
COPY code /usr/share/nginx/html