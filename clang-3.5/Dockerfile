FROM walberla/buildenv-ubuntu-clang:3.5

MAINTAINER Nerijus Arlauskas <nercury@gmail.com>

# remove cmake

RUN apt-get update \
 && apt-get remove --purge -y \
    cmake \
 && apt-get autoremove -y && apt-get autoclean -y \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# build latest cmake

ARG cmake_sources="https://cmake.org/files/v3.6/cmake-3.6.0.tar.gz"
LABEL cmake-version=3.6.0

RUN cd /opt \
 && mkdir src \
 && curl -s $cmake_sources | tar -xz --strip-components=1 -C src \
 && cd src \
 && ./bootstrap \
 && make -j8 \
 && make install \
 && cd .. \
 && rm -rf src
