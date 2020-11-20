FROM tensorflow/tensorflow:latest-gpu

LABEL maintainer="chrisplus.jiang@gmail.com"

# apt update
RUN apt update && apt upgrade -y

# apt install utils
RUN apt intall -y wget vim

# apt install opencv related
RUN apt install -y libsm6 libxext6 libxrender-dev libgl1-mesa-glx

# install basic packages
RUN pip install -U pip setuptools \
    && pip --no-cache-dir install \
        numpy \
        scipy

# install opencv and coco tools
RUN pip --no-cache-dir install \
    opencv-python \
    pycocotools