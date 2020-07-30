FROM tensorflow/tensorflow:2.2.0-gpu

LABEL maintainer="chrisplus.jiang@gmail.com"

# update

RUN apt update && apt upgrade -y

# install basic packages
RUN pip install -U pip setuptools \
    && pip --no-cache-dir install \
        numpy \
        pandas \
        h5py \
        scipy \
        scikit-learn \
        matplotlib \
        opencv-python



# install pytorch
RUN pip --no-cache-dir install \ 
    torch \
    torchvision

# install tensorflow dataset
RUN pip --no-cache-dir install \
    tensorflow-datasets \
    tensorflow-hub \
    tensorflow-metadata
