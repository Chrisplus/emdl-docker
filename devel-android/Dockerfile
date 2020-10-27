FROM tensorflow/tensorflow:latest-devel

MAINTAINER Shiqi Jiang "chrisplus.jiang@gmail.com"

ARG BAZEL_VERSION=3.7.0
ARG NDK_VERSION=r21d

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

RUN mkdir -p /root/Android/Sdk/cmdline-tools/
ENV ANDROID_HOME=/root/Android/Sdk

RUN cd /root/Android/Sdk/cmdline-tools \
    && wget https://dl.google.com/android/repository/commandlinetools-linux-6609375_latest.zip \
    && unzip commandlinetools-linux-6609375_latest.zip \
    && rm commandlinetools-linux-6609375_latest.zip \
    && ./tools/bin/sdkmanager --update \
    && yes | ./tools/bin/sdkmanager --licenses \
    && ./tools/bin/sdkmanager 'build-tools;30.0.1' 'platforms;android-30' 'ndk-bundle' 'ndk;21.3.6528147' 'ndk;20.1.5948944' 'ndk;19.2.5345600' 'ndk;18.1.5063045'

# RUN cd /root/Android/Sdk \
#     && wget https://dl.google.com/android/repository/android-ndk-${NDK_VERSION}-linux-x86_64.zip \
#     && unzip android-ndk-${NDK_VERSION}-linux-x86_64.zip \
#     && mv android-ndk-${NDK_VERSION} ndk-bundle \
#     && rm android-ndk-${NDK_VERSION}-linux-x86_64.zip

# RUN cd /root/Android \
#     && wget https://github.com/bazelbuild/bazel/releases/download/${BAZEL_VERSION}/bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh \
#     && chmod a+x ./bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh \
#     && ./bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh
