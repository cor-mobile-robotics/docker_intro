# Docker-intro




This repository gives an indepth explanaition in how to use Docker. With Docker you can containerize applications and can include everything to build and run this application in an isolated environment. This gives the possibility to easily install dependencies without changing the file system of the host. It makes it also highly portable, since this isolated environment can be started on any machine with the same architecture (example, amd or arm). And you can just restart the container when something goes wrong.


## Installation


If docker is already installed and you can do,
```
docker ps
```
without getting an permission error, you can skip the following steps and go down to the tutorials.

To install docker (https://docs.docker.com/engine/install/ubuntu/):
```
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
And then to give superuser priviliges to docker:
```
sudo groupadd docker
sudo usermod -aG docker $USER
```
Where you have to change $USER to your own user name. Now restart your machine and check if the permission warning is gone when you run,
```
docker ps
```


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









