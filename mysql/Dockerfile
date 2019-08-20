FROM amazonlinux:2

#Util
RUN yum -y install systemd-sysv yum-utils

#日本語設定
RUN yum install -y glibc-langpack-ja && yum clean all
ENV LANG ja_JP.utf8
ENV LC_ALL ja_JP.utf8

RUN unlink /etc/localtime
RUN ln -s /usr/share/zoneinfo/Japan /etc/localtime

RUN yum localinstall -y https://dev.mysql.com/get/mysql80-community-release-el7-1.noarch.rpm -y

#mysql8.0リポジトリの無効化
RUN yum-config-manager --disable mysql80-community

#mysql5.7リポジトリの有効化
RUN yum-config-manager --enable mysql57-community

CMD ["/sbin/init"]


