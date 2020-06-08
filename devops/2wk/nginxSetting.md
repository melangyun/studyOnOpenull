# NginX 설정파일 파일 변경

## bash
```bash
$ find / -name nginx.conf
$ cd /etc/nginx
$ cp nginx.conf nginx-copy.conf
$ ci nginx.conf
$ nginx -s reload
# 바뀐 설정을 적용하기 위해 Nginx 재가동
```

```conf
server {
listen 80 default_server; 
listen [::]:80 default_server; 

server_name _;
root /usr/share/nginx/html/Fastcampus-web-deploy;
# root로 접속시 맨 처음으로 기본으로 찾는 디렉토리 이후  file path만 적으면 된다.

# Load configuration files for the default server block. include /etc/nginx/default.d/*.conf;
location / { 
}

location ~* /(album|signin) {
  root /usr/share/nginx/html/Fastcampus-web-deploy/page;
}
# ~ : 대소문자 구분하여 적용
# ~* : 대소문자 구분 없이 적용
# Nginx 가 처리하는 URL이 album 혹은 signin 에 매칭되는 지 확인
# 해당 URL 이 매칭된다면 Nginx root 디렉토리를 해당 블럭에 적힌 디렉토리로 변경

location /api {
proxy_pass {ec2_private_dns/ip}:8080
}

# proxy_pass
# 들어온 요청을 다른 웹 서버 or WAS로 전달 (reverse proxy)
# DB 서버와 연결되어 있는 WAS의 ip와 포트 번호를 감출 수 있음(보안)

error_page 404 /404.html; 

location = /40x.html {
}

error_page 500 502 503 504 /50x.html; 

location = /50x.html {
} 

}

```
위 설정 외에도 
    - `worker_processes auth(or number);`
    몇 개의 thread를 사용 할 것인지 정의, CPI core수를 넣어주면 된다.
    auto로 설정하면 해당 머신의 CPU core 수 만큼 자동으로 설정됨
    - `worker_connections 1024;`
    worker thread 당 최대 몇 개의 connection을 처리할 것인지 정의
    최대 처리량 = worker_processes * worker_connections
    - reverse proxy, Load balancer, web cache 서버 등 설정에 따라 다양하게 사용 가능!
