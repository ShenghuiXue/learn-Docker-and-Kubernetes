# learn-Docker-and-Kubernetes
My notes for the Udemy course: [Docker and Kubernetes: The Complete Guide](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/)

## Manipulating Containers with the Docker Client
### Creating and running a Container from a docker image
* run with the default command
  ```s
  docker run <image name>
  docker run hello-world
  ```
* running the docker with the alternate command
  ```s
  docker run <image name> <alternative command>
  docker run busybox ls # run ls command for the busybox image
  ```

### Listing running containers
* `docker ps`
  * This command list all the running containers
    ```s
    docker run busybox ping google.com # running a docker image for longer time 
    docker ps
    
    # output 
    # CONTAINER ID   IMAGE     COMMAND             CREATED          STATUS          PORTS     NAMES
    # e4507d3ba1d6   busybox   "ping google.com"   37 seconds ago   Up 36 seconds             blissful_knuth
    ```
* `docker ps --all`
  * This command list all containers that have been created
    ```s
    docker ps --all
    docker ps -a
    ```

### Container life cycle
* Creating a container
  * `docker run` command is actually running two separate processes: `docker create` and `docker start`
    ```s
    docker create <image name> # create an image
    docker start <container id> # start a container
    ```