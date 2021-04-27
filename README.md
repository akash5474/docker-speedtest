# docker-speedtest
This is the docker image for [@henrywhitaker3/Speedtest-Tracker](https://github.com/henrywhitaker3/Speedtest-Tracker)

## Available Platforms
- amd64
- arm64
- arm/v7

## Getting Started

To pull the image run

    docker pull bricksoft/speedtest

which will automatically pull the right image for your platform.
<br/>
<br/>
Now you can create your container:
```
docker create \
      --name=speedtest \
      -p 8765:80 \
      -v /path/to/data:/config \
      -e OOKLA_EULA_GDPR=true \ 
      --restart unless-stopped \
      bricksoft/speedtest
```

Or you can create your container using `docker-compose`: 
```docker-compose
version: '3.3'
services:
    speedtest:
        container_name: speedtest
        image: bricksoft/speedtest
        ports:
            - 8765:80
        volumes:
            - /path/to/data:/config
        environment:
            - TZ=
            - OOKLA_EULA_GDPR=true
        restart: unless-stopped
```