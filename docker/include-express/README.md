
```shell
# Create docker image
$ docker build -t include-express-image .

# Docker run git-cline-nestjs
$ docker run --name include-express -p 3002:3000 include-express-image

http://localhost:3002  
```