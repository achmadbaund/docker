# docker
image on docker

https://www.youtube.com/watch?v=Ra1CetTcSeo&t=19s

- Installing the docker
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin docker-compose
```
- 
- Masuk ke folder source code ne
- buat file docler-compose.yml
```

contoh Konfig:

version: '3.7'
services:
    db:
        image: postgres:14.1-alpine
        restart: always
        environment:
            - POSTGRES_USER=celias
            - POSTGRES_PASSWORD=PASSNYA
        ports:
            - '6666:6666'
        volumes: 
            - ./db:/var/lib/postgresql-14/data
    app:
        build: 
            context: .
            dockerfile: .docker/Dockerfile
        image: "tumbas_by_celia"
        ports: 
            - "8080:80"
        volumes:
            - ./:/var/www/html/
```
- Buat Folder .docker isinya file (DockerFile & vhost.conf jika menggunakan Apache / HTTPD)
- sudo usermod -a -G docker $USER
- ketik perintah sudo docker-compose up -d (jika belum terinstal install terlebih dahulu docker-compose nya)
- Untuk melihat list container = sudo docker ps
- Untuk login ke docker = sudo docker exec -it <containernya> bash   /   sudo docker exec -it Laravel_nginx /bin/sh
- Untuk Pull = sudo docker-compose pull
- Untuk Update perubahan pada file docker = sudo docker composer up -d
- Untuk melihat log = sudo docker-compose log
- Untuk Stop dan remove semuanya = sudo docker-compose down
- Untuk Build kembali = sudo docker-compose build
- Untuk Stop Running Docker = sudo docker stop <containerID>
- Untuk Compose UP sekalian Build Perubahan pada DockerFile = docker-compose up --build -d
- Untuk merestart service = docker restart <Container Name>
- Docker Remove Setting = docker rm -f <NAMA DOCKER>
