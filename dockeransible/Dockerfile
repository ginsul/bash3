FROM python:3.10.5-slim

ENV ANSIBLE_CORE_VERSION 2.13.3

RUN pip3 install --upgrade pip cffi && \
  pip3 install ansible-core==${ANSIBLE_CORE_VERSION} && \
  pip3 install ansible && pip3 install ansible-lint && \
  pip3 install mitogen jmespath && \
  pip install --upgrade pywinrm && \
  rm -rf /root/.cache/pip

RUN pip3 install napalm && pip3 install napalm-ansible && ansible-galaxy install Juniper.junos && pip3 install jxmlease

COPY ansible.cfg /etc/ansible/ansible.cfg

RUN mkdir /network /folderdiff /folderbackup

WORKDIR /ansible