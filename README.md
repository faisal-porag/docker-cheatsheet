## Docker-Cheatsheet
All necessary docker commands 


# Manage containers

`docker ps`

```bash
$ docker ps
$ docker ps -a
$ docker kill $ID
```

Manage `container`s using ps/kill.


# Images
```bash
docker images
docker image ls
docker iamge ls -q  //Get only id
docker image rm $(docker iamge ls -q) //Delete unused images
docker image rm $(docker container ls -q) //Delete unused containers
docker container rm $(docker container ls -q) //Delete unused containers
docker container rm $(docker container ls -a -q) //Delete unused containers
docker container rm $(docker container ls -aq) //Delete unused containers
docker container rm -f $(docker container ls -aq) //Delete unused containers forcefully
```
