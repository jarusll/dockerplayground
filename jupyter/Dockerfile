FROM python:slim-buster
# replce sh with bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

WORKDIR /jupyter

RUN pip install jupyter

# setup javascript kernel
RUN apt-get update
RUN apt-get install nodejs npm -y
RUN npm install -g ijavascript --unsafe-perm
RUN ijsinstall

# # setup data dir
RUN mkdir /data_dir
