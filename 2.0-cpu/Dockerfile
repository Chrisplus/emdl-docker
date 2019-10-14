FROM tensorflow/tensorflow:2.0.0-py3

LABEL maintainer="chrisplus.jiang@gmail.com"


# install basic packages
RUN pip install -U pip setuptools \
    && pip --no-cache-dir install \
        numpy \
        pandas \
        h5py \
        scipy \
        scikit-learn \
        matplotlib



# install pytorch
RUN pip --no-cache-dir install \ 
    torch \
    torchvision

# install tensorflow dataset
RUN pip --no-cache-dir install \
    tensorflow-datasets \
    tensorflow-hub \
    tensorflow-metadata
