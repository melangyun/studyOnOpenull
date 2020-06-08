---
description: AWC Linux 기준
---

# EC2 NginX Setting

## EC2 접속

```bash
$ ssh -i ./{pem}.pem ec2-user@{DNS주소}
```

## NginX 설치, 실행

```bash
$ sudo su
# 앞으로의 작업을 root권한으로 변경
$ amazon-linux-extras install nginx1.12
# nginx 설치
# Amazon Linux Extras 리포지 토리를 통한 최신 소프트웨어 패키지 제공!
$ nginx
```

정상적으로 설치되었을 경우 브라우저로 DNS 접속시 Nginx가 실행된다.

> Amazon Linux2를 기반으로 하는 AWS AMI를 활용하여 EC2를 생성하고 SSH 클라이언트로 접속하여 해당 VM에 웹서버(NginX)를 `설치 후 웹 브라우저를 통해 DNS:80포트에서 확인하였습니다.

# Docker 로 설치
```bash
# 관리자 권한으로 실행
$ sudo su
# amazon-linux-extras 레포지토리를 활용해 docker 설치
$ amazon-linux-extras install docker
# docker 데몬 실행
$ service docker start
# dockerhub에서 nginx 이미지 다운로드
$ docker pull nginx:latest
# 도커 이미지 조회
$ docker images
# Nginx 실행
$ docker run -d -p 8080:80 --name NginX nginx:latest
# nginx:latest 이미지를 기반으로 docker container 실행
$ docker ps -a
```