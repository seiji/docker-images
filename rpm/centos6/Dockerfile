FROM centos:6

RUN yum update -y && yum install -y -q yum-utils build-essential git tar wget which tcl zlib-devel jemalloc-devel
RUN yum groupinstall -y 'Development tools'
RUN yum clean all

ADD fedora.repo /etc/yum.repos.d/fedora.repo
RUN rpm --import http://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-6
RUN rpm -ihv http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm

WORKDIR /opt/rpmbuild

ADD apache /opt/rpmbuild/apache/
ADD redis /opt/rpmbuild/redis/
ADD handlersocket /opt/rpmbuild/handlersocket/

