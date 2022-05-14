
```shell
# Create docker image
$ docker build -t git-clone-nestjs-image .

# Docker run git-cline-nestjs
$ docker run --name git-clone-nestjs -p 3001:3000 git-clone-nestjs-image

http://localhost:3001  
```