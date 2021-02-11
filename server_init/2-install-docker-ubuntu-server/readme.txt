sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
sudo apt update
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker


#helpful commands
# sudo docker ps -a
# sudo docker rm container_name
# docker run hello-world
# docker images
# docker rmi hello-world
# sudo !! - for when you didn't allow docker to run without 'sudo'
# docker images may be committed to a docker repository, for version control. Images are built on top of one another with a layered approach.