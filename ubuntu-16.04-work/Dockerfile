# To install this file, go to location of this file and run:
# $ sudo docker build --network=host -t image_name:tag docker_file
#
# If using greater equal to ubuntu 18.04: (internet not working from within docker)
# $ sudo ln -sf /run/systemd/resolve/resolv.conf /etc/resolv.conf
# Verify: cat /etc/resolv.conf
# 
# execute docker:
# $ sudo docker run -v /host_path/:/docker_path/ -p 8888:8888 -i -t ubuntu-16.04-py3.5-caffe2-cpu:0.1 /bin/bash
# (inside docker) $ jupyter notebook --ip=172.17.0.2 --port=8888 --allow-root
# 
# Can get docker_ip using ifconfig command inside docker
# Change mount below according to your directories
# Prefer use volumes: its a docker feature

FROM ubuntu:16.04
LABEL maintainer="saideep@colostate.edu"

# update and install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    libgoogle-glog-dev \
    libgtest-dev \
    libiomp-dev \
    libleveldb-dev \
	liblmdb-dev \
 	libopencv-dev \
	libopenmpi-dev \
	libsnappy-dev \
	libprotobuf-dev \
	openmpi-bin \
	openmpi-doc \
	protobuf-compiler \
	python3-dev \
	python3-pip \
	libgflags-dev \
	python3-setuptools \
	cmake \
	vim \
	net-tools \
	wget \
	tmux

# all python packages required
RUN pip3 install --no-cache-dir \
	flask \
	graphviz \
	jupyter \
	matplotlib \
	pydot \
	python-nvd3 \
	pyyaml \
	requests \
	scikit-image \
	scipy \
	tornado \
	future \
	six \
	protobuf \
	hypothesis \
	numpy \
	typing \
	hypothesis \
	pandas \
	wheel \
	sklearn \
	# starting 1.6 not working on older machines (No AVX) 
	tensorflow==1.5 \
	keras 

RUN pip3 install tqdm seaborn

RUN apt install htop tree && \
	git config --global user.email "saideep@rams.colostate.com" && \
	git config --global user.name "saideep" 


# create an area to work in
WORKDIR /home/saideep/
RUN chmod -R a+w /home/saideep
