# Docker image installation

Pull the image from [link](https://hub.docker.com/_/mongo)

```bash 
docker pull mongo:latest
```

After downloaded the images, we can create a container with the following command:

```bash
docker run --name some-mongo -d mongo:latest
```

If we want to set a volume to store the date within our host so we should run the following command:

```bash
docker run --name some-mongo -v /my/own/datadir:/data/db -d mongo:latest
```

Before running the above command we should create the directory in the host where we want to store the data. 

To access MongoDB from the hots, it need a network to connect with. So, we need to create a docker network and then connect the MongoDB container to the it.

To create the network we need to run the following command:

```bash
docker network create network-name 
```

Then we connect the container to network:

```bash
docker network connet network-name container-name
```

Also, we can use docker compose to the same but in a easiest way. We need to create a docker compose fail:

```yaml
version: '3.1'

services:

  catalog-mongo:
    image: mongo
    restart: always
    container_name: catalog-mongo
    networks:
      - catalog-net
    volumes:
      - ./storage-dir/:/data/db

networks:
  catalog-net:
    driver: bridge

```

Then, we run docker compose we the above file:

```bash
docker-compose build && docker-compose up --force-recreatye -d
```

