FROM python:slim-buster
# replce sh with bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

WORKDIR /jupyter

# setup env for python
RUN python3 -m pip install virtualenv
RUN virtualenv jupyter
RUN ls /jupyter
RUN source /jupyter/jupyter/bin/activate

# install jupyter
RUN pip install jupyter

# setup javascript kernel
RUN apt-get update
RUN apt-get install nodejs npm -y
RUN npm config set prefix $HOME
RUN npm install -g --unsafe-perm ijavascript
RUN node /root/lib/node_modules/ijavascript/bin/ijsinstall.js

# setup data dir
RUN mkdir /data_dir
RUN mkdir /config_dir
