[<ins> 1. Starting with Docker </ins>](docker_starting.md)  
[2. Dockerfile](docker_dockerfile.md)  
[3. Management in Docker](docker_management.md)  
[4. Docker image size reduction](docker_sizereduction.md)  
[5. Docker GPU passthrough](docker_gpu_passthrough.md)  
[6. Docker inside Visual Studio Code](docker_vscode.md)  
[7. Docker and ROS](docker_ros.md)  
[8. Docker Compose](docker_compose.md)  
[9. Docker with the Jetson platform](docker_jetson.md) 

___

# 1. Starting with Docker

First, a few key words are explained to understand some basic components of the Docker environment. These key words will be used frequently during the tutorials, so make sure you understand them. 

### Dockerfiles
The Dockerfiles can be seen as a bleu-print with instruction for creating a given Docker image. It states what environment you want to use, which programs or utilities need to be installed and the setup of the environment. But Why do we want to pass a Dockerfile around and not the image that it creates? Well that is due to size. A Dockerfile is nothing more than commands in a text file that defines your image, the image itself can be a few 100 Mb to a few Gb's in size. How to build a Dockerfile will be further explained in the section [Dockerfile](docker_dockerfile.md). 

### Images
The images created or stored on your system can be used to start up containers. These images contain the full system layout, like ubuntu, and all folders and files that you or somebody else put into the image when it was created. As already mentioned, these files can become large in size. Due to the size, make sure that you don't have to many different images on your system or regurly clean up unwanted images. If you have the Dockerfile or you can pull a remote Docker image, you can easily create the image again. In the section [Docker management](docker_management.md), we will further go into how you can easily manage your images. 

### Containers
Containers are created from images, and together with initialisation commands specify how the container looks like and what it needs to do. These containers can be  made to run only one script or go as far as making an interactive environment where you can develop your applications. In the next section we show two simple examples as a start. When you are working inside the container, everything will be stored in it's environment like terminal inputs and changed files. Note: these changes are only stored in the container file and not automatically in the image that created the container. Storing the container as an image will be explaint in the [Docker management](docker_management.md) section. 


## A first start

To start the journey into the Docker environment, we will first give you two simple examples to play with. We will not explain here in detail what is happening, this is just a first view of docker images. 

### Hello World
One of the first examples is an container that starts up, prints the line "Hello from Docker!" together with some further information from Docker and then closes again. Afterwards the container will automatically be removed, so you are not left with an unwanted container. How we remove the image itself will be discussed in [Docker management](docker_management.md). 

```
docker run --rm hello-world
```

### ROS environment
Another example is an interactive container with ROS Noetic installed.

```
docker run --rm --it ros:noetic
```
After the images is pulled and the container is started, you will see that you are now running a terminal inside the container. Let's start a roscore,
```
roscore
```
You will see that a ROS core is started with Distro set to Noetic. If another terminal is opened that is not running inside the container but on the host, and run the command,
```
rostopic list
```
an error is given since the roscore runs in the protective environment of the container. The section [Docker and ROS](docker_ros.md) will go further on how to use ROS with Docker. There, some examples will be shown how ROS can communicate between different containers and the host.    



__

That is all to quickly start with Docker, for more information on docker see below for the next step.

[<ins> 1. Starting with Docker </ins>](docker_starting.md)  
[2. Dockerfile](docker_dockerfile.md)  
[3. Management in Docker](docker_management.md)  
[4. Docker image size reduction](docker_sizereduction.md)  
[5. Docker GPU passthrough](docker_gpu_passthrough.md)  
[6. Docker inside Visual Studio Code](docker_vscode.md)  
[7. Docker and ROS](docker_ros.md)  
[8. Docker Compose](docker_compose.md)  
[9. Docker with the Jetson platform](docker_jetson.md)  









