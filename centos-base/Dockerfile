FROM centos:centos7

RUN yum update -y \
  && yum -y install vim htop wget git bash-completion curl yum-plugin-fastestmirror

RUN wget http://rpms.famillecollet.com/enterprise/remi-release-7.rpm

RUN yum install remi-release-7.rpm -y

RUN yum clean all
