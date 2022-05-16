```shell
# Create docker image
$ docker build -t include-express-image .

# Docker run git-cline-nestjs
$ docker run --name include-express -p 3002:3000 include-express-image

http://localhost:3002  
```

### AWS ECR public

```shell

$ aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com
$ aws ecr get-login-password --region ap-northeast-2 | docker login --username AWS --password-stdin 122708793557.dkr.ecr.ap-northeast-2.amazonaws.com

# AWS ECR tag settings
$ docker tag <docker-image-ID> public.ecr.aws/<registry_alias>/<my-web-app> 
$ docker tag e9ae3c220b23 public.ecr.aws/o8w89kq8/astraiosis

# AWS ECR Upload docker image
$ docker push public.ecr.aws/<registry_alias>/<my-web-app>
$ docker push public.ecr.aws/o8w89kq8/astraiosis
```