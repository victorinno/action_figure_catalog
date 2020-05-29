# action_figure_catalog

## Features
* List the different categories of products
* Include products specifications
* Add multimedia resources such as videos and pics.
* Send push notifications, "Whatsapp" like messages with new releases and important info
* Get feedback. Create surveys to get valuable information from your customers
* Geolocate your distributors
* Include your social networks twitter, facebook, youtube...
* Let your contact you through phone, email or a form. With only one touch on the screen, and they'll contact you!


## Monitoring

[Prometheus](https://prometheus.io/)


## Api Gateway
[Kraden](https://www.krakend.io/features/)



sudo docker network create jenkins
sudo docker volume create jenkins-docker-certs
sudo docker volume create jenkins-data
sudo docker container run --name jenkins-docker --rm --detach --privileged --network jenkins --network-alias docker --env DOCKER_TLS_CERTDIR=/certs --volume jenkins-docker-certs:/certs/client --volume jenkins-data:/var/jenkins_home --publish 2376:2376 docker:dind
sudo docker container run --name jenkins-blueocean --rm --detach --network jenkins --env DOCKER_HOST=tcp://docker:2376 --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1 --publish 8080:8080 --publish 50000:50000 --volume jenkins-data:/var/jenkins_home --volume jenkins-docker-certs:/certs/client:ro jenkinsci/blueocean

sudo docker run -d --name express-gateway-data-store -p 6379:6379 redis:alpine
sudo docker run -d --name express-gateway --link express-gateway-data-store:express-gateway-data-store -v /my/own/datadir:/var/lib/eg -p 9080:9080 -p 9876:9876 -p 10443:0443 express-gateway
sudo docker pull ggcaponetto/express-gateway-gui
sudo docker run -e EXPRESS_GATEWAY_ADMIN_URL=http://host.docker.internal:9876 -e PROXY_PORT=9877 -d -p 5000:5000 -p 9877:9877 -it ggcaponetto/express-gateway-gui