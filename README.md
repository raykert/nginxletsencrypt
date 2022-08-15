# Documentation for my Nginx reverse proxy configuration


## Nginx with letsencrypt Docker Compose file 


This is the Docker compose file for deploy Nginx in a docker container.
It's a image from linuxserver named as Swag

Docker compose file contain an example for deploy
[docker-compose.yml](docker-compose.yml)

<p>&nbsp;</p>

## Authors

- [@raykert](https://github.com/raykert)
<br/>

<br/>

## Documentation

[Documentation Docker Hub](https://hub.docker.com/r/linuxserver/swag)
[Documentation GitHub](https://github.com/linuxserver/reverse-proxy-confs)  

## Environment Variables

To run this project, you will need to add the following environment variables to your .yml file

For environment i configured:

    environment:
      - PUID=1000
      - PGID=1000
      - TZ=America/Santo_Domingo
      - URL=domain.com
      - VALIDATION=http
      - EMAIL=mail@mail.com
      - ONLY_SUBDOMAINS=false
      - STAGING=false #optional   

## Cert files

The cert file provided by letsencrypt is in /config/keys
<br/><br/>

## Reverse proxy

For configure reverse proxy for your services you can use two ways:

- As a folder: domain.com/yourNameservice
- As subdomain: yourNameservice.domain.com

The path for put the files is /config/nginx/proxy-confs, normally there are several example file depending of your services. For example i use portainer, jenkins and qBittorrent. View the example files.
I am using jenkins in 8080 port, portainer in 9000 and qbittorrent in 8081.

<br/>
<br/>

**Note:** I am using that services in docker container.  
**Note:** If you are going to use subdomain you haver to create the CNAME registry in the domain configuration.

This the example files:

| Service | File |
| ------- | ------ |
| Jenkins subfolder | [jenkins.subfolder.conf](proxy-confs/jenkins.subfolder.conf) |
| Jenkins subdomain | [jenkins.subdomain.conf](proxy-confs/jenkins.subdomain.conf) |
| Portainer subfolder | [portainer.subfolder.conf](proxy-confs/portainer.subfolder.conf) |
| Portainer subdomain | [portainer.subdomain.conf](proxy-confs/portainer.subdomain.conf) |
| QBittorrent subfolder | [qbittorrent.subfolder.conf](proxy-confs/qbittorrent.subfolder.conf) |  

<br/>

<br/>

## Network configuration

Your docker services must run in the same docker network with the swag container, It's mandatory.

**Note:** Remember restart swag container once you modify the reverse proxy configuration files for your domain or subfolder services.
