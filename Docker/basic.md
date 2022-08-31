# Basic of docker

##### Interactive shell in the new container
``` shell 
sudo docker run -i -t ubuntu /bin/bash
```
` -i ` - flag keeps STDIN open from the container, even if we’re not attached to it.
` -t ` flag is the other half and tells Docker to assign a pseudo-tty to the container we’re about to create

---
##### Alternative way to go Interactive shell
If we have container in docker like `ubunt` with command `bin/bash`
``` shell 
sudo docker start name_of_container 
sudo docker attach name_o_container
```
` start ` - –
` attach ` - –

---
##### Listing all containers 
``` shell 
sudo docker container ls --all 
```
` --all ` - Show all containers

is the same/similar as
``` shell 
sudo docker ps -a
```

---
##### Run container in background with pseudo TTY
``` shell 
sudo docker run -d -t --name name_your_container image
```
` -d ` -  detached mode: run the container in the background
` -t ` - Allocate a pseudo-TTY. The default is false.

---
##### Go to the Ubuntu container to interact with bash 
``` shell 
sudo docker exec -t -i your_container bash
```
` -t ` - Allocate a pseudo-TTY. The default is false.
` -i ` - Keep STDIN open even if not attached

---
##### Go to the Ubuntu container to interact with bash 
``` shell 
sudo docker exec -d your_container your_command 
# docker exec -d ubuntu_container touch /etc/new_config_fiel
```
` -t ` - Allocate a pseudo-TTY. The default is false.
` -i ` - Keep STDIN open even if not attached

---
##### Stop the container
Send  SIGTERM
```shell
sudo docker stop your_conteiner 
```
or send SIGKILL
```shell
sudo docker kill your_conteiner 
```

---
##### Automatic restart  
restart always no mater what exit code you get 
``` shell 
sudo docker run --restart=always --name daemon_alice -d ubuntu
/bin/sh -c "while true; do echo hello world; sleep 1; done"
```

restart only 5 times 
``` shell 
--restart=on-failure:5
```

---
##### Finding out more about our container
showing all about container with JSON format
``` shell 
sudo docker inspect your_container
```
cheeking the status of container using this method  
```shell
sudo docker inspect --format='{{ .State.Running }}' your_container
```
or even container address ip 
```shell
sudo docker inspect --format '{{ .NetworkSettings.IPAddress }}' your_container
```
---

##### Deleting a container
```shell
sudo docker rm your_contiener 
```
all
``` shell 
sudo docker rm -f `sudo docker ps -a -q`
```

---
##### Search for images in repo
``` shell 
sudo docker search kali
```

---
##### Log
```shell
sudo docker logs your_container
```

```shell
sudo docker run --log-driver="syslog" --name name_container -d ubuntu /bin/sh 
-c "while true; do echo hello world; sleep 1; done"
```


