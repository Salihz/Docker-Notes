[![N|Solid](https://www.bobit.us/images/bobit-logo.png)](https://www.bobit.us/)

# Docker Installation
To get started with Docker Engine on CentOS, make sure you [meet the prerequisites], then [install Docker].

[meet the prerequisites]: <https://docs.docker.com/engine/install/centos/#prerequisites>
[install Docker]: <https://docs.docker.com/engine/install/centos/#installation-methods>
[re-enable it]: <https://wiki.centos.org/AdditionalResources/Repositories>
[prerequisites]: <https://docs.docker.com/engine/install/ubuntu/#prerequisites>
[Windows]: <https://hub.docker.com/editions/community/docker-ce-desktop-windows/>

# Prerequisites
# OS requirements

To install Docker Engine, you need a maintained version of CentOS 7. Archived versions aren’t supported or tested.
The **centos-extras** the repository must be enabled. This repository is enabled by default, but if you have disabled it, you need to [re-enable it].
The **overlay2** storage driver is recommended.
# Uninstall old versions
Older versions of Docker were called docker or docker-engine. If these are installed, uninstall them, along with associated dependencies.

```sh
$ sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```
It’s OK if **yum** reports that none of these packages are installed.
The contents of **/var/lib/docker/**, including images, containers, volumes, and networks, are preserved. The Docker Engine package is now called **docker-ce**.
# Setup Repository
Install the **yum-utils** package (which provides the **yum-config-manager** utility) and set up the **stable** repository.
```sh
$ sudo yum install -y yum-utils

$ sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```
# Install Docker Engine
Install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:
```sh
$ sudo yum install docker-ce docker-ce-cli containerd.io
```
# Install Docker Engine on Ubuntu
To get started with Docker Engine on Ubuntu, make sure you meet the [prerequisites], then install Docker.
To install Docker Engine, you need the 64-bit version of one of these Ubuntu versions:
- Ubuntu Focal 20.04 (LTS)
- Ubuntu Eoan 19.10
- Ubuntu Bionic 18.04 (LTS)
- Ubuntu Xenial 16.04 (LTS)

Docker Engine is supported on **x86_64 (or amd64), armhf, and arm64** architectures.
# Uninstall Old Versions
Older versions of Docker were called **docker**, **docker.io**, or **docker-engine**. If these are installed, uninstall them:
```sh
$ sudo apt-get remove docker docker-engine docker.io containerd runc
```
It’s OK if **apt-get** reports that none of these packages are installed.
The contents of **/var/lib/docker/**, including images, containers, volumes, and networks, are preserved. The Docker Engine package is now called **docker-ce**.
# Install Using Repository
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.
Update the **apt** package index and install packages to allow apt to use a repository over HTTPS:
```sh
$ sudo apt-get update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```
Add Docker’s official GPG key:
```sh
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Verify that you now have the key with the fingerprint **9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88**, by searching for the last 8 characters of the fingerprint.
```sh
$ sudo apt-key fingerprint 0EBFCD88
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```
Use the following command to set up the **stable** repository. To add the nightly or test repository, add the word **nightly** or **test** (or both) after the word stable in the commands below.
> Note: The **lsb_release -cs** sub-command below returns the name of your Ubuntu distribution, such as **xenial**. 
Sometimes, in a distribution like **Linux Mint**, you might need to change **$(lsb_release -cs)** to your parent Ubuntu distribution. 
For example, if you are using Linux Mint Tessa, you could use **bionic**. 
Docker does not offer any guarantees on untested and unsupported Ubuntu distributions
```sh
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
# Install Docker Engine
Update the apt package index, and install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:
```sh
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd 
```
# Install with apt Repo
```sh
$ apt update
$ apt install docker.io -y
```
# Install Docker On Windows

Docker Desktop for [Windows] is the Community version of Docker for Microsoft Windows. You can download Docker Desktop for [Windows] from Docker Hub.