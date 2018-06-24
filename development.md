# Development

## Building
To build the client libraries and server docker image execute:

    mvn package
    
## Starting the server

Execute

    F9C_DOMAIN=<yourdomain> docker-compose up

in the projects root directory. This will start with listening port 8443. 

## Deploying to a cloud instance

Use the included *cloud-config.yml* to create a f9c cloud instance 
(see https://cloudinit.readthedocs.io/en/latest/index.html). 

After the instance is running log into it and execute

    certbot certonly --standalone -d <yourdomain>  --email <youremail> --agree-tos --no-self-upgrade -n

to generate the letsencrypt certificates (<yourdomain> has to resolve the machine).

To start the server processes use 

    F9C_DOMAIN=<yourdomain> docker-compose -f /etc/docker-compose.yml up -d

Use 

    docker-compose -f /etc/docker-compose.yml pull

to update the images.
