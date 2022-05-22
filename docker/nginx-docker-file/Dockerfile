FROM ubuntu:20.04

# Linux 패키지 설치
RUN apt-get update
RUN apt-get install nginx -y

# nigx 설정 파일에 명령어 삽입
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

VOLUME ["/data", "/etc/nginx/site-enabled", "/var/log/nginx"]

# Directory 이동
WORKDIR /etc/nginx

# Docker 실행 시 자동 실행 명령어
CMD ["nginx"]

EXPOSE 80
EXPOSE 443