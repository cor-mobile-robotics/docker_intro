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

# 6. Docker inside Visual Studio Code


This tutorial shows how you can create containers from images or restart/stop existing containers in Visual Studio Code. We also show you how to attach Visual Studio Code to a container, so you can develop inside of it.

## Contents:
* [1. Visual Studio Code Extensions](#1-visual-studio-code-extensions)
* [2. Docker Side Bar](#2-docker-side-bar)
* [3. Attach VS Code to a Running Container](#3-attach-vs-code-to-a-running-container)



## 1) Visual Studio Code Extensions

The following extensions are used in this module:
- Dev Containers (Open any folder or repository inside a Docker container and take advantage of Visual Studio Code's full feature set.)
- Docker (Makes it easy to create, manage, and debug containerized applications.)



## 2) Docker Side Bar

The Docker side bar can be opened using the extension icon. There you will see two important sections, the containers and the images that are currently on your system. To start a new container, right-click on one of the images and then select `Run` or `Run Interactive` as visible in the figure below.

> Note: Interactive creates a container where you can open terminals or work in the container. If you only run a container, it will open and run some code that you specified and close again. Like the `hello-world` container in the example below. Using `Run` will only create the container which will echo hello-world and then close again. Using `Run Interactive` will be identical to `Run` exept it doesn't close the container.

Existing containers can also be stopped and started from the side bar. Right-click on one of the containers that is not running (red square) and press `Start`, when the container is running a green triangle will be shown.

![Alt text](images/create_container.png?raw=true "create container") ![Alt text](images/start_container.png?raw=true "start container") ![Alt text](images/attach.png?raw=true "attached VS code")





## 3) Attach VS Code to a Running Container

Now that we have a running container, we can attach Visual Studio Code to it or, incase you only want a terminal interface, attach a Shell. Right-click on the running container and select `Attach Shell` or `Attach Visual Studio Code`. In the case of `Attach Visual Studio Code`, a new Visual Studio Code window will open which will be attached to the container. This will be visible in the green lower-left corner, denoting the image name and container name. You can now open folders or open terminals inside the container and start development inside of the container. 

![Alt text](images/attach_container.png?raw=true "attached VS code to container")





___

That is all for using Docker with Visual Studio Code, for more information on docker see below for the next step.
 
[7. Docker and ROS](docker_ros.md)  


