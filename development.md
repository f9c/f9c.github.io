# Development

## Building
To build the client libraries and server docker image execute:

    mvn package
    
## Starting the server

Execute

    docker-compose up

in the projects root directory. This will start with listening port 8443

## Deploying

Use the included *cloud-config.yml* to deploy f9c to a cloud server 
(see https://cloudinit.readthedocs.io/en/latest/index.html). The server will start on the default https port 443.