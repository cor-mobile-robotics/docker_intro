
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

# 9. Reducing the size of Docker images

Lot of packages to build application is not needed when application is build. When these are left on the image, it creates an unnecessary big sized image. When enough storage is available, it doesn't create big problems. But it can quickly become a problem when different people have their own images on a machine. Therefore we can create stages inside the dockerfile. Many libraries are only needed to build an application and not for running application. Therefore, we can install the dependencies and the built the application. After the application is made, we only port the application to the next stage and remove all the unnecessary dependencies of the build. 





















___

That is all for docker compose, for more information on docker see below for the next step.


[1. Starting with Docker](docker_starting.md)  
[2. Dockerfile](docker_dockerfile.md)  
[3. Management in Docker](docker_management.md)  
[4. Docker image size reduction](docker_sizereduction.md)  
[5. Docker GPU passthrough](docker_gpu_passthrough.md)  
[6. Docker inside Visual Studio Code](docker_vscode.md)  
[7. Docker and ROS](docker_ros.md)  
[8. Docker Compose](docker_compose.md)  
[9. Docker with the Jetson platform](docker_jetson.md) 

















