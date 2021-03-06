# Docker Demo - To get started with dockers :whale:
[Link for Common Commands](https://github.com/vermavinay982/docker-demo/blob/main/README.md#few-other-important-commands)

## Running the Code Above
```
docker build -t colorapp . 
docker run --rm -it -p 8000:8080 --name blue-app -e APP_COLOR=blue colorapp
```

### Analogy to remember order
```
port   -p your's:docker's
volume -v your's:docker's
```


### If want to run docker without ```sudo```
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: 

If want to run docker without using sudo everytime - you need to add your user (who has root privileges) to docker group.
For this run following command

```
sudo groupadd docker
sudo gpasswd -a $USER docker
newgrp docker or (logout/login your system)
docker run hello-world
```
[More Deep Info Here - about using docker w/o sudo](https://askubuntu.com/questions/477551/how-can-i-use-docker-without-sudo)

## Few Other Important Commands 
---

```
docker exec -it <container name> bash
docker exec -it <container name> python3
docker attach <container name>
docker cp mycontainer:/filename.txt filename.txt
```
### Saving and Loading Image - Without Internet
```
docker save -o <path for generated tar file> <image name>
docker save --output hello.tar colorapp
docker load --input hello.tar
```
### Run Python with display
```
docker run --rm -it --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xauthority:rw" python
```
