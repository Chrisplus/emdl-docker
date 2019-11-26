FROM tensorflow/tensorflow:devel-py3

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
    && ./tools/bin/sdkmanager 'build-tools;29.0.2' 'platforms;android-29' 'ndk-bundle' 'ndk;20.1.5948944' 'ndk;19.2.5345600' 'ndk;18.1.5063045'

# RUN cd /root/Android/Sdk \
#     && wget https://dl.google.com/android/repository/android-ndk-r18b-linux-x86_64.zip \
#     && unzip android-ndk-r18b-linux-x86_64.zip \
#     && mv android-ndk-r18b ndk-bundle \
#     && rm android-ndk-r18b-linux-x86_64.zip

RUN cd /root/Android \
    && wget https://github.com/bazelbuild/bazel/releases/download/0.29.1/bazel-0.29.1-installer-linux-x86_64.sh \
    && chmod a+x ./bazel-0.29.1-installer-linux-x86_64.sh \
    && ./bazel-0.29.1-installer-linux-x86_64.sh

