# Docker-intro




This repository gives an indepth explanaition in how to use docker 








## Installation


If docker is already installed and you can do,
```
docker ps
```
without getting an permission error, you can skip the following steps.

To install docker:
```

```
And then to give superuser priviliges to docker:
```
sudo groupadd docker
sudo usermod -aG docker $USER
```
Where you have to change $USER to your own user name. Now restart and check if the permission warning is gone.



## Tutorials

[1. Starting with Docker](docs/docker_starting.md)
[2. Dockerfile](docs/docker_dockerfile.md)
[3. Management in Docker](docs/docker_management.md)
[4. Docker image size reduction](docs/docker_sizereduction.md)
[5. Docker GPU passthrough](docs/docker_gpu_passthrough.md)
[6. Docker inside Visual Studio Code](docs/docker_vscode.md)
[7. Docker and ROS](docs/docker_ros.md)
[8. Docker Compose](docs/docker_compose.md)
[9. Docker with the Jetson platform](docs/docker_jetson.md)









