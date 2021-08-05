FROM tensorflow/tensorflow:latest-gpu

LABEL maintainer="chrisplus.jiang@gmail.com"

# apt update
RUN apt update && apt upgrade -y

# apt install utils
RUN apt install -y wget vim git file

# apt install opencv related
RUN apt install -y libsm6 libxext6 libxrender-dev libgl1-mesa-glx

# install basic packages
RUN pip install -U pip setuptools \
    && pip --no-cache-dir install \
        numpy \
        scipy

# setup node and npm
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh |bash

RUN export NVM_DIR="$HOME/.nvm" \
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" \
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"

RUN nvm install node

RUN npm install -g yarn

# install opencv and coco tools
# RUN pip --no-cache-dir install \
#     opencv-python \
#     pycocotools
