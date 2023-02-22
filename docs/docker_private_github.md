










# How to pull in private repo during docker build

To pull in private repositories, you have to use your ssh key. But we don't want our private key to be compromised. Thats were the buildkit from docker comes into play. To use this,
```
export DOCKER_BUILDKIT=1

docker build --ssh default -t image_name .
```
here we added the --ssh option to mount the ssh socket into the build environment. This let's the builder use your ssh key credentials without the possibility of someone else obtaining your private key.
Furthermore, in your dockerfile use the option "--mount=type=ssh" to use your ssh cridentials in a specific layer. For example,
```
RUN --mount=type=ssh \
    git clone git@github.com:test/ros_pkg.git ~/catkin_ws/src/ros_pkg
```

when you have a password protected key use:




# Using docker build on a remote machine
Now to build a dockerfile on a remote machine that needs private repositories, we are going to use the ssh credentials of the host machine. From the host machine we are going to create a ssh tunnel to the remote machine using:
```
ssh -A name@ip-address
```
Now that the tunnel is created we are going to authenticate to github
```
ssh -T git@github.com
```
Now the docker build command need to be changed to :
```
export DOCKER_BUILDKIT=1

docker build --ssh default==${SSH_AUTH_SOCK} -t image_name .
```