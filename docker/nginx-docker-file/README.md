```shell
# Create docker image
$ docker build -t nginx-docker-image .

# Docker run nginx
$ docker run --name nginx-docker-container -d -p 80:80 nginx-docker-image

http://localhost
```
