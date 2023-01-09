

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

# 5. GPU acceleration inside docker
In this tutorial we use a NVIDIA graphics card for GPU acceleration inside Docker containers. There is a possibility that this tutorial is going to be extended to other manufactures, but for now it is only NVIDIA based.


>Note: You should already have the NVIDIA CUDA toolkit installed and should be able to run the command `nvidia-smi`, which displays your gpu driver version and CUDA version.

First we need to setup the GPG key from the package repository for the [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker)
```
distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
      && curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg \
      && curl -s -L https://nvidia.github.io/libnvidia-container/$distribution/libnvidia-container.list | \
            sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
            sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
```
Now the package listing can be updated and the NVIDIA Container Toolkit can be installed,
```
sudo apt-get update
sudo apt-get install -y nvidia-docker2
```

Restart Docker to complete the installation
```
sudo systemctl restart docker
```

Now you should be able to run and build containers with CUDA available. This can be tested using an example CUDA base container,
```
sudo docker run --rm --gpus all nvidia/cuda:11.6.2-base-ubuntu20.04 nvidia-smi
```

___

That is all to get GPU acceleration inside containers, for more information on docker see below for the next step.
 
[6. Docker inside Visual Studio Code](docker_vscode.md)  







