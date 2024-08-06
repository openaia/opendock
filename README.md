# opendock

Build Docker Images for building Buildroot/Yocto/Debos based EdgeAIA.

# Install docker

First, remove any old versions of Docker if they are installed:
```
sudo apt remove docker docker-engine docker.io containerd runc
sudo apt update
```

Set up Docker's official repository:
```
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
```

Now, install Docker:
```
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
```

Add Your User to the Docker Group:
```
sudo groupadd docker
sudo usermod -aG docker $USER
```

Verify the Installation:
```
docker run hello-world
```

# Run

Ubuntu 22.04:

```
docker run -ti --privileged --net host -v `pwd`:/home/build/shared -w /home/build/shared ghcr.io/edgeble/opendock/ubuntu:22.04
```
