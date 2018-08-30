#[Install docker ce](https://docs.docker.com/install)
The following tutorial is for Ubuntu only

* Step 1: Install some necessary system tools
```shell
sudo apt-get update
sudo apt-get -y install apt-transport-https ca-certificates curl software-properties-common
```
* Step 2: Install the GPG certificate
Here we will use aliyun software source
```shell
curl -fsSL http://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
```
* Step 3: Write the software source information
```shell
sudo add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
```
* Step 4: Search for available versions Docker-CE
```shell
apt-cache madison docker-ce
```

* Step 4: Update and install Docker-CE
```shell
sudo apt-get -y update
sudo apt-get -y install docker-ce=18.06.1~ce~3-0~ubuntu
```
replace "18.06.1~ce~3-0~ubuntu" with the version you want

* Step 5: Installation verification
```shell
sudo docker version
```
You'll get the following output
```
Client:
 Version:           18.06.1-ce
 API version:       1.38
 Go version:        go1.10.3
 Git commit:        e68fc7a
 Built:             Tue Aug 21 17:24:58 2018
 OS/Arch:           linux/amd64
 Experimental:      false

Server:
 Engine:
  Version:          18.06.1-ce
  API version:      1.38 (minimum version 1.12)
  Go version:       go1.10.3
  Git commit:       e68fc7a
  Built:            Tue Aug 21 17:23:24 2018
  OS/Arch:          linux/amd64
  Experimental:     false
```

* Step 6: Manage docker as a non-root user

You may notice that we need ```sudo``` permission to run docker command
in step 5, if you don't want to preface docker command with ```sudo```,
you can create a Unix group called ```docker``` and add users to it. 

1. create the '''docker''' group
```shell
sudo groupadd docker
```

2. Add your user to the ```docker``` group
```shell
sudo useradd -aG docker $USER
```

3. Verify that you can run docker commands without ```sudo```
```shell
docker run hello-world
```



#[Install nvidia-docker](https://docs.docker.com/install)



