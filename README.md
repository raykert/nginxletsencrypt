
# Nginx with letsencrypt Docker Compose file

This is the Docker compose file for deploy Nginx in a docker container.
It's a image from linuxserver named as Swag


## Authors

- [@raykert](https://github.com/raykert)


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

