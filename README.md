# asterisk-nginx-docker-task
asterisk-nginx-docker-task


#ADD
sudo usermod -aG docker $USER

#NEW GROUP
newgrp docker


#UP- build your image 
##DockerfileToImage

docker-compose up --build -d


#Start the Docker Service
sudo systemctl start docker
sudo systemctl enable docker

#CHECK STATUS
sudo systemctl status docker
