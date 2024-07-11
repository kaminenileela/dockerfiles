Docker image == Bare minimum OS + App run time + system packages and dependencies + App code = image
Docker container == running instance of image is called container.


To install docker on RHEL

* sudo yum install -y yum-utils
* sudo yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
* sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
* sudo systemctl start docker
* systemctl status docker
* systemctl enable docker 

some docker we need to run--- come out of root and run them
when docker is installed, it will create docker group.Users who r in docker group or root user can only run docker commands 
* usermod  -aG docker ec2-user--> to add user to secondary group usermod -aG <group name> <username>
then logout of system and then login to run docker commands

* docker ps ----> it will show running containers
* docker ps -a ---> all containers with any status
* docker images ---> list down the images
* docker pull nginx ---> to take images from docker hub
* username, image name and version ----> TAG is version
* docker pull alpine --->OS which is less than 10 MB
* docker pull nginx:alpine
* docker create <image>:tag ---> to create container from image
* docker start <container id>---> container will start running
* * docker run  = docker pull + docker create + docker run  * *
* docker rm -f <container id> --> to stop running containers forcefully
* docker stop <container id> ---> to stop running container
* docker rmi <image id>---> to delete image
* docker rmi `docker images -a -q`---> to delete all images
* docker rm `docker ps -a -q` ---> to delete all containers
* docker run nginx ---> this runs in foreground
* docker run -d nginx ---> to run in background (also called detach mode)

![alt text](docker.JPG)

server has 65535 ports, even docker container has 65535 ports.
How can you access docker container from internet?
By enabling the port, we need to open host port that can redirect traffic to container.

docker run -d -p <host-port>:<container-port>
docker run -d -p 80:80 nginx --->host port our wish ---> container port is fix
* ex: docker run -d -p 8000:80 nginx--->if we do <aws instance ip address:8000> -->we get access 

docker logs <container id> ---> to see logs of container 
docker logs -f <container id> ---> -f is follow the logs of container 
docker inspect <container id> ---> we will get full information of container 
docker inspect <image id> ---> to get information of image 
docker exec -it <container id> bash (execute interactive terminal)---> 

* Docker file 
It is declarative way of creating custom images. keep all the instructions in a file (i.e docker file) and build the image.

docker build -t url/username/image-name:tag . ( dot represents current directory. by default docker build command checks for docker file)

* instructions

FROM:
from should be the fitrst instruction to represent base OS
FROM image-name:tag

RUN:
we will use RUN instruction to install packages and configure them. RUN instruction will execute at the time of image creation.




