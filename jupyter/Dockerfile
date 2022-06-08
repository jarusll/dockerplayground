FROM python:slim-buster
# replce sh with bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

WORKDIR /jupyter

# jupyter lab setup
RUN pip install jupyterlab
RUN pip install --upgrade jupyterlab-vim jupyterlab-git

# setup javascript kernel
RUN apt-get update
RUN apt-get install npm nodejs pandoc texlive-xetex texlive-fonts-recommended texlive-plain-generic git -y
RUN npm i -g ijavascript --unsafe-perm
RUN ijsinstall

# setup ruby kernel
RUN apt install ruby-dev -y # installs ruby 2.5
RUN gem install io-console -v 0.5.9 # last version to support ruby 2.5
RUN gem install rake # iruby depends on rake
RUN gem install iruby
RUN iruby register --force

# setup data dir
RUN mkdir /data_dir
