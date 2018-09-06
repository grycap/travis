FROM ubuntu:14.04
MAINTAINER alpegon3@upv.es

# Update and install all the necessary packages
RUN apt-get update \
  && apt-get install -y --no-install-recommends \
     software-properties-common \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /usr/share/doc \
  && rm -rf /usr/share/man

# Install Ansible.
RUN apt-add-repository -y ppa:ansible/ansible \
  && apt-get update \
  && apt-get install -y --no-install-recommends \
     ansible python-pyasn1 python-openssl python-urllib3 \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /usr/share/doc \
  && rm -rf /usr/share/man

# Install ansible-galaxy dep
RUN easy_install pip && pip install ndg-httpsclient

# Install Ansible inventory file
RUN printf '%s\n' '[local]' 'localhost ansible_connection=local' > /etc/ansible/hosts
