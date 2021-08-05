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
ENV NVM_DIR="/root/.nvm"
RUN . "$NVM_DIR/nvm.sh" && nvm install node && npm install -g yarn

# install tensorflow.js
RUN pip install tensorflowjs
# install opencv and coco tools
# RUN pip --no-cache-dir install \
#     opencv-python \
#     pycocotools
