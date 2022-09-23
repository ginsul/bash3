FROM python:3.10.5-slim

COPY requirements.txt requirements.txt

RUN pip3 install --upgrade pip cffi && \
  pip3 install -r requirements.txt && \
  rm -rf /root/.cache/pip /requirements.txt && \
  mkdir /network /folderdiff /folderbackup

RUN ansible-galaxy install Juniper.junos

COPY ansible.cfg /etc/ansible/ansible.cfg

WORKDIR /ansible
