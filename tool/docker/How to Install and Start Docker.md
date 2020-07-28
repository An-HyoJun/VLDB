# How to Install and Start Docker

## Thanks
- https://github.com/meeeejin/til/blob/master/docker/mysql-with-docker-volume.md

## Install Docker Engine
## Install Docker Engine

1. Update the `apt` package index:

```bash
$ sudo apt-get update
```

2. Install the necessary packages to allow `apt` to use a repository over HTTPS:

```bash
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

3. Add Docker’s official GPG key:

```bash
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Verify that you now have the key with the fingerprint:

```bash
$ sudo apt-key fingerprint 0EBFCD88
    
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```

4. Set up the stable repository:

```bash
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

5. Install the latest version of Docker Engine:

```bash
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

### Test Docker Installation

1. Verify that Docker Engine - Community is installed correctly by running the hello-world image:

```bash
$ sudo docker run hello-world

Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
ca4f61b1923c: Pull complete
Digest: sha256:ca0eeb6fb05351dfc8759c20733c91def84cb8007aa89a5bf606bc8b315b9fc7
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```

2. Run `docker image ls` to list the hello-world image that you downloaded to your machine:

```bash
$ sudo docker image ls
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hello-world         latest              fce289e99eb9        15 months ago       1.84kB
```

3. You can check the status of all the containers using the below command:

```bash
$ sudo docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                     PORTS                               NAMES
2eeed464cd9f        hello-world         "/hello"                 2 minutes ago       Exited (0) 2 minutes ago                                       objective_perlman
```

4. You can stop one or more running containers:

```bash
$ sudo docker stop [container-name]
```