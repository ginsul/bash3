FROM python:3.9.15-slim

COPY requirements.txt requirements.txt

RUN pip3 install --upgrade pip cffi && \
  pip3 install -r requirements.txt && \
  rm -rf /root/.cache/pip /requirements.txt && \
  mkdir /network /folderdiff /folderbackup /batfish

RUN ansible-galaxy install Juniper.junos && \
    ansible-galaxy install --force batfish.base && \
    rm -rfd /usr/local/lib/python3.9/site-packages/ansible_collections/netbox

COPY ansible.cfg /etc/ansible/ansible.cfg

WORKDIR /ansible
