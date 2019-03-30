# Docker Images

Install docker with:
```shell
sudo apt install docker.io
```
Post install on linux run docker without sudo:
```Shell
# Create the docker group.
sudo groupadd docker

# Add your user to the docker group.
sudo usermod -aG docker $USER

# Log out and log back in so that your group membership is re-evaluated.
# If issues follow: docs.docker.com/install/linux/linux-postinstall/

```


A collection of docker files that I use or have made.

1. ubuntu-16.04-py3.5-caffe2-cpu
Working with caffe2 and python3 and Jupyter.

2. ubuntu-16.04-work
Day to day image to run exxperiments on larger and faster machines.
