
```shell
# Create docker image
$ docker build -t include-nestjs-image .

# Docker run git-cline-nestjs
$ docker run --name include-nestjs -p 3003:3000 include-nestjs-image

http://localhost:3003  
```