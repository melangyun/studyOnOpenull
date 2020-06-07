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
$ nginx
```

정상적으로 설치되었을 경우 브라우저로 DNS 접속시 Nginx가 실행된다.

