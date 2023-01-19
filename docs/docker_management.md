
[1. Starting with Docker](docker_starting.md)  
[2. Dockerfile](docker_dockerfile.md)  
[3. Management in Docker](docker_management.md)  
[4. Docker image size reduction](docker_sizereduction.md)  
[5. Docker GPU passthrough](docker_gpu_passthrough.md)  
[6. Docker inside Visual Studio Code](docker_vscode.md)  
[7. Docker and ROS](docker_ros.md)  
[8. Docker Compose](docker_compose.md)  
[9. Docker with the Jetson platform](docker_jetson.md) 

___

# 3. Management of docker images and running containers


To check al existing images stored
```
docker images
```
this will show all base images, layers and final images that are tagged by a name.

TO DO: example images

To clear all not used layers
```
docker rmi --force $(docker images -f "dangling=true" -q)
```

To remove specific layers or images
```
docker rmi --force <IMAGE ID>
```
where IMAGE ID can be retrieved using 
```
docker images
```






To reset and remove unwanted occupied space by docker
```
docker system prune
```







```
docker ps
docker ps -a
docker image ls
docker info
docker start <name>
dockerdocker exec -it <name> bash
 stop <name>
docker container rm <name> 
```



## Build commands



## Run commands













___

That is all for managing your containers and images, for more information on docker see below for the next step.
 
[4. Docker image size reduction](docker_sizereduction.md)  

