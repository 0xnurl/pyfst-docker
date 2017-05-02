FROM ubuntu:16.04
MAINTAINER Nur Lan <nurxlan@gmail.com>
LABEL description="PyFST image using Python 3.6 and OpenFST 1.6.0"

# Use bash (Ubuntu default is dash)
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Ubuntu packages required for building Python and OpenFST
RUN apt-get update && apt-get install -y wget gcc g++ make libbz2-dev libssl-dev gdb git

# Install Python 3.6
RUN cd /tmp && wget https://www.python.org/ftp/python/3.6.0/Python-3.6.0.tgz && tar xzvf Python-3.6.0.tgz && cd Python-3.6.0 && ./configure && make && make install

# Install OpenFST
RUN cd /tmp && wget http://www.openfst.org/twiki/pub/FST/FstDownload/openfst-1.6.0.tar.gz && tar xzvf openfst-1.6.0.tar.gz && cd openfst-1.6.0 && ./configure --enable-far --enable-pdt --enable-mpdt && make && make install

# Install virtualenv and Python packages
RUN pip3 install virtualenv && cd ~ && virtualenv -p $(which python3) venv && source ./venv/bin/activate && export CFLAGS="-std=c++11" && pip install pyfst