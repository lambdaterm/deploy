FROM centos:centos7
MAINTAINER Alexander Karpich <avkarpich@gmail.com>

RUN yum -y update
RUN yum -y groupinstall "Development Tools"
RUN yum -y install java java-devel wget
RUN wget http://dl.bintray.com/sbt/rpm/sbt-0.13.5.rpm; rpm -i sbt-0.13.5.rpm;

RUN mkdir -p /root/.ssh/
RUN echo -e "Host github.com\n\tStrictHostKeyChecking no\n" >> /root/.ssh/config
RUN git clone https://github.com/ymn/deploy /app

WORKDIR /app
RUN sbt compile