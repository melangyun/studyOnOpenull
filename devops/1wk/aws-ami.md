# AWS AMI

* 서버 인스턴스의 기반이 되는 이미지
* 윈도우 CD, iso와 같은 개념
* Amazon 에서 제공하는 빅데이터, 웹서비스 등 각 기능별로 빌드한 이미지를 사용하거나 다른 사람이 공유하는 이미지도 사용 가능

## with AWS ELB 
> EC2 인스턴스를 추가할 때 마다 새롭게 설정(Nginx 설치, 설정 파일 변경, 실행) 해야 할까?
>
> 그렇지 않다! 모든 설치와 설정이 완료된 EC2로 만들어 AMI로 빌드하면 같은 EC2를 생성할 수 있다. (like CD)

## AWS AMI 생성

1. AMI 빌드를 위해 스냅샷을 찍을 EC2 인스턴스에 접속
2. `sudo su`
3. `systemctl enable nginx`
**AMI를 기준으로 자동으로 EC2 인서턴스가 생성될 때 NginX 프로세스를 자동으로 실행하기 위해 `systemctl`에 nginx 실행을 등록한다.**