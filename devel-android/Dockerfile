FROM tensorflow/tensorflow:latest-devel-py3

MAINTAINER Shiqi Jiang "chrisplus.jiang@gmail.com"


# upgrade packages
RUN apt update && apt upgrade -y

# install basic packages
RUN pip install -U pip setuptools \
    && pip --no-cache-dir install \
        numpy \
        pandas \
        h5py \
        scipy \
        scikit-learn \
        matplotlib

RUN mkdir -p /root/Android/Sdk



RUN cd /root/Android/Sdk \
    && wget https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip \
    && unzip sdk-tools-linux-4333796.zip \
    && rm sdk-tools-linux-4333796.zip \
    && ./tools/bin/sdkmanager --update \
    && yes | ./tools/bin/sdkmanager --licenses \
    && ./tools/bin/sdkmanager 'build-tools;26.0.1' 'platforms;android-26'

RUN cd /root/Android/Sdk \
    && wget https://dl.google.com/android/repository/android-ndk-r18b-linux-x86_64.zip \
    && unzip android-ndk-r18b-linux-x86_64.zip \
    && mv android-ndk-r18b ndk-bundle \
    && rm android-ndk-r18b-linux-x86_64.zip

