# Nextcloud
# Networking
Create docker network to connect Nextcloud and NGINX
```
sudo docker network create nc-net
```
## Environment variables
Run ```cd nextcloud && cp env.sample .env``` and update the variables according to your setup ```sudo vim .env```
## Run container
```
docker-compose up -d
```
## Scan manually added files
Change ownership and group
```
sudo chown -R www-data yelizondo/
sudo chgrp -R www-data yelizondo/
```
Scan files
```
sudo docker exec -ti --user www-data nextcloud_nextcloud-frontend_1 /var/www/html/occ files:scan --all
```
# NGINX
## Copy SSL certs to ```nginx/ssl/```
## Run container
```
cd nginx
sudo docker-compose build && sudo docker-compose up -d
```