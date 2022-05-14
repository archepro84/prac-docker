FROM ubuntu:16.04
LABEL version='1.0.0'

USER root

SHELL [ "/bin/bash", "-l", "-c" ]

# replace shell with bash so we can source files
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Update, upgrade linux apt package manager
RUN apt-get update
RUN apt-get upgrade -y

# install curl, git
RUN apt-get install curl \
    git \
    -y

# NVM Environment Update
ENV NVM_DIR /usr/local/nvm
ENV NODE_VERSION 16

# Create Directory
RUN mkdir -p $NVM_DIR

# install node version manager
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

# NVM install node
RUN source $NVM_DIR/nvm.sh \
    && nvm install $NODE_VERSION \
    && nvm alias default $NODE_VERSION \
    && nvm use default

# Add nvm.sh to .bashrc for startup...
RUN echo "source ${NVM_DIR}/nvm.sh" > $HOME/.bashrc && \
    source $HOME/.bashrc

# NVM Node Path Update
ENV NODE_PATH $NVM_DIR/v$NODE_VERSION/lib/node_modules
ENV PATH      $NVM_DIR/versions/node/v$NODE_VERSION/bin:$PATH

# Move Work directory
WORKDIR /opt/app

# nvm use node:16
RUN nvm use 16

# github project install
RUN git clone -b Simple-IaC --single-branch https://github.com/archepro84/prac-ORM.git

# directory move
WORKDIR ./prac-ORM/typeorm

# project install
RUN npm install

# Start node project
CMD npm run start --prefix /opt/app/prac-ORM/typeorm