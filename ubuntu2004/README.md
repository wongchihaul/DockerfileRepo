Build a ubuntu 20.04 image with openssh-server installed.

```bash
## build image
docker build -t ubuntu2004-ssh .
## run a container and map port 22 to 26122 in local
docker run -d -p 26122:22 --name myubuntu ubuntu2004-ssh /usr/sbin/sshd -D
## Log in via ssh
ssh -p 26122 root@localhost
```