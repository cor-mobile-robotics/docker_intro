# Docker-intro

docker run -it --rm

-it means start interactive shell after container is build
--rm remove the container afterwards, so it is not left on your system

bash added at end of docker run means that bash terminal is opened in the container




error in VS code connect error
terminal paste:
- sudo groupadd docker
- sudo usermod -aG docker $USER

then restart



# multiple terminals to same container
to start the docker container
```
docker run -it <image_id> bash
```
To open more terminals connected to the same container
```
docker exec -it <container_id> bash
