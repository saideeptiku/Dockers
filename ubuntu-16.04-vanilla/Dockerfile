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
RUN apt-get update && \
      apt-get -y install sudo

# add a new user and ad them to user
RUN useradd -m saideep && echo "saideep:saideep" | chpasswd && adduser saideep sudo


# create an area to work in
WORKDIR /home/saideep/
RUN chmod -R a+w /home/saideep

USER docker
CMD /bin/bash



