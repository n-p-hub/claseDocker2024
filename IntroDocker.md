## Intro a Docker

### Material de Referencia:
https://docs.docker.com/get-started/

https://labs.play-with-docker.com/

### Permisos en Linux
Para agregar a usaurio a grupo Docker:
```
sudo usermod -aG docker $USER 
```

### Imágenes Docker

Docker Registry (Almacenaje de imágenes docker):
https://hub.docker.com/ (es el registry oficial de imágenes de Docker)

Para listar imágenes existentes en el sistema:
```
docker images
```

### Docker Container

Crear de contenedor Hello World:
```
docker run hello-world 
```

Crear de contenedor de NGINX:
```
docker run -d nginx 
```

Asociar de Puertos:
```
docker run -d -p 8080:80 nginx 
```

Listar de contenedores en ejecución:
```
docker ps
```

Listar de contenedores en ejecución y detenidos:
```
docker ps -a
```

Ver los logs de un contenedor:
```
docker logs <container_name>
```

Parar la ejecución de un contenedor:
```
docker stop <container_name>
```

Eliminar contenedor:
```
docker rm <container_name>
```

Ingresar al shell del contendor:
```
docker exec -ti <container_name> bash
docker exec -ti <container_name> sh
```

### Mysql
Image: https://hub.docker.com/_/mysql
```
docker run --name un-mysql -e MYSQL_ROOT_PASSWORD=test1234 -p 33333:3306 -d mysql
```

### RabbitMQ
Image: https://hub.docker.com/_/rabbitmq
```
docker run -d --name some-rabbit rabbitmq:3
```

### Dockerfile Spring Boot
[IR](/springboot/Dockerfile) 

Build de Dockerfile:
```
docker build -t springbootapp .
```

### Docker Compose
[docker-compose.yml](/docker-compose.yml) 

Para Mysql (NO RECOMENDADO PARA ENTORNOS PRODUCTIVOS)
```
command: --default-authentication-plugin=mysql_native_password
```

Ejecutar de los servicios declarados en el docker compose:
```
docker-compose up -d
```

Parar de los servicios declarados en el docker compose:
```
docker-compose down
```

### Upload a Docker Registry
```
docker login
docker build . -t usuario/imagenejemplo:0.0.1
docker push usuario/imagenejemplo:0.0.1
```

Github Packages (Registry de Github):
https://github.com/features/packages