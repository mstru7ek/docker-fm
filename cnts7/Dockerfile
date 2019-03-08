#
#
# Lightwey container with Centos 7 and develope tools
#
#

FROM centos:7

RUN yum install -y vim less 

# JQ - json extractor/formater 
RUN curl -v -L https://github.com/stedolan/jq/releases/download/jq-1.6/jq-linux64 -o "/usr/bin/jq"
RUN chmod a+x /usr/bin/jq

# find character encoding from file
RUN yum install -y bind-utils


# OpenSSL
RUN yum install -y openssl

RUN yum install -y git

# OpenSSH server, client
RUN yum install -y openssh openssh-server openssh-clients openssl-libs

RUN ssh-keygen -A

RUN adduser git
RUN echo "git" | passwd -f --stdin git 


ENTRYPOINT ["/usr/sbin/sshd","-D"]