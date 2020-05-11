# Docker Commands

```sh
docker images
```

```sh
docker ps
docker ps -a
```

```sh
docker build --tag tag_name
docket build -t tag_name .
```

```sh
docker tag image_name tag
```

```sh
docker run --rm -i -t image_name
docker run -d -p 8080:80 --restart=always --name=requested_name image_name
```

```sh
docker rm -f container_id_or_container_name
docker rmi image_name
```

```sh
docker exec -i -t container_name "cmd"
```

```sh
docker start -i image_name
docker stop image_name
```

```sh
docker-compose down
docker-compose up -d
```

```sh
docker search image_name
```

```sh
alias docker="winpty docker"
```

| Description | Link |
| ------ | ------ |
| - | -|