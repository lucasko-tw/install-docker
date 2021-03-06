# install-docker

### Install Docker on CentOS 7

```sh
### Install Docker 
sudo yum install -y yum-utils   device-mapper-persistent-data   lvm2
sudo yum-config-manager     --add-repo     https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install -y docker-ce
yum list docker-ce --showduplicates | sort -r

sudo usermod -aG docker root
sudo usermod -aG docker centos
sudo reboot

### Install Docker Compose
sudo yum install epel-release
sudo yum install -y python-pip
sudo pip install docker-compose

sudo systemctl enable docker
sudo systemctl start docker
```

### Login to AWS ECR

```sh
aws ecr get-login --no-include-email --region eu-west-1
```
It will output a new command like following.

```sh
docker login -u AWS -p XXXXXXX== https://1111111111.ecr.eu-west-1.amazonaws.com
```

Single Command Line to Login

```sh
eval $(aws ecr get-login --no-include-email --region eu-west-1)
```
