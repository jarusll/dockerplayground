FROM python:slim-buster
# replce sh with bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

WORKDIR /jupyter

# jupyter lab setup
RUN pip install jupyterlab
RUN pip install --upgrade jupyterlab-vim jupyterlab-git

# setup javascript kernel
RUN apt-get update
RUN apt-get install npm nodejs git -y
RUN npm i -g ijavascript --unsafe-perm
RUN ijsinstall

# # setup data dir
RUN mkdir /data_dir
