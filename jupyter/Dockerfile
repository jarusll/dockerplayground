FROM python:slim-buster
# replce sh with bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

WORKDIR /jupyter

# jupyter lab setup
RUN pip install jupyterlab
RUN pip install --upgrade jupyterlab-vim

# setup javascript kernel
RUN apt-get update
# install nvm
RUN apt-get install curl make g++ -y
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | /bin/bash
RUN /bin/bash -ci 'nvm install 14'
RUN /bin/bash -ci 'npm install -g ijavascript --unsafe-perm'
RUN ijsinstall

# # setup data dir
RUN mkdir /data_dir
