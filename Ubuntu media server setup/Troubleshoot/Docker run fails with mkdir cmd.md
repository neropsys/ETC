# Docker run with mkdir cmd fails with read-only file system error

## TLDR;
[Source](https://stackoverflow.com/a/52566470)

## Cause
docker gets installed using snap store on Ubuntu setup, giving only read-only file system

## Solution
1. Remove docker from snap & install official one
```
snap remove docker
```
2. Remove docker dir & old version
```
rm -r /var/lib/docker
sudo apt-get remove docker docker-engine docker.io
```
3. Follow official docker installation [guide](https://docs.docker.com/engine/install/ubuntu/)

