# pickup-docker
Enlarging the docker knowledge with a guide line

#### Docker basic commands
docker images
docker ps
docker ps -a
docker container rm container_id
docker run -it -rm -d -p 8888:8080 tomcat:8.0 sleep 1000

#### Creating docker image from debina:jessie using command
docker run -it debian:jessie
ls
apt-get update && apt-get install -y git
git --version
ctrl + c
docker ps -a
docker commit container_id datacrud/debian:1.00
docker images
docker run -it datacrud/debian:1.00
ls
git
ctrl + c

#### Creating docker image from debina:jessie using Dockerfile
echo FROM debian:jessie > Dockerfile

......edit the docker file using text editor....... (see <a href="https://github.com/sabbiryan/pickup-docker/blob/master/Dockerfile">Dockerfile</a>)

docker build -t datacrud/debina . (. means Dockerfile present in current direcotry)
docker build -t datacrud/debina . --no-cache=true
docker images
docker run container_id


#### Dockerfile keywords
FROM (define image source)
RUN (run instrations)
CMD (run on container startup)
COPY (copy files or diretories to container)
ADD (copy, download, unpack compress files)

#### Image push to docker hub
docker tag container_id datacrud/debian:1.01
docker tag container_id dockerhubuserid/debian:1.01
docker login --username=dockerhubusername
Login Succeeded
docker push dockerhubuserid/debian:1.01
