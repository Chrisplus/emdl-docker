FROM tensorflow/tensorflow:latest-devel

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

RUN mkdir -p /root/Android/Sdk/cmdline-tools/
RUN export ANDROID_HOME=/root/Android/Sdk



RUN cd /root/Android/Sdk/cmdline-tools \
    && wget https://dl.google.com/android/repository/commandlinetools-linux-6609375_latest.zip \
    && unzip commandlinetools-linux-6609375_latest.zip \
    && rm commandlinetools-linux-6609375_latest.zip \
    && ./tools/bin/sdkmanager --update \
    && yes | ./tools/bin/sdkmanager --licenses \
    && ./tools/bin/sdkmanager 'build-tools;30.0.1' 'platforms;android-30' 'ndk-bundle' 'ndk;21.3.6528147' 'ndk;20.1.5948944' 'ndk;19.2.5345600' 'ndk;18.1.5063045'
# RUN cd /root/Android/Sdk \
#     && wget https://dl.google.com/android/repository/android-ndk-r18b-linux-x86_64.zip \
#     && unzip android-ndk-r18b-linux-x86_64.zip \
#     && mv android-ndk-r18b ndk-bundle \
#     && rm android-ndk-r18b-linux-x86_64.zip

# RUN cd /root/Android \
#     && wget https://github.com/bazelbuild/bazel/releases/download/0.29.1/bazel-0.29.1-installer-linux-x86_64.sh \
#     && chmod a+x ./bazel-0.29.1-installer-linux-x86_64.sh \
#     && ./bazel-0.29.1-installer-linux-x86_64.sh

