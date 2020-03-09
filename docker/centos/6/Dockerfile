FROM centos:6
MAINTAINER alpegon3@upv.es

# Install Ansible and other requirements.
RUN yum -y install epel-release \
 && yum -y update \
 && yum -y install \
      sudo \
      which \
      ansible \
      python-pip \
      iproute \
 && yum clean all

RUN pip install urllib3 pyOpenSSL ndg-httpsclient pyasn1

# Install Ansible inventory file
RUN printf '%s\n' '[local]' 'localhost ansible_connection=local' > /etc/ansible/hosts
