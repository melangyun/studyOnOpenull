---
description: EC2 Intro
---

# EC2

## EC2란?

* AWS네서 제공하는 가성서버 \(Vritual Machine, VM\)
* Amazon Linux, Cent Os, Ubuntu, Windows 등 다양한 OS제공
* 원하는 사양을 관리자가 직접 선택할 수 있음
* 필요할 때마다 사용 / 중지가 가능

> **Virtual Machine**
>
> 실제 하드웨어와 직접적인 통신이 없는 가상 컴퓨터  
> 물리 머신 위에 독립적 OS 실행이 가능한 논리적인 가상 OS를 생성하여 실행한다.
>
> * 하나의 서버에서 여러 OS실행.
> * 자원\(CPU, Memory 등\) 의 공

## 제공하는 OS

### Amazon linux2

* AWS에서 제공하는 차세대 Lunux 운영체제
* Amazon Linux Extras 리포지토리를 통해 최신 소프트웨어 패키지 제공 \(ubuntu의 apt-get과 비슷한 느낌인듯.\)
* Container 환경에 최적화 된 OS

### Cent Os

보안 부분에 가장 안정적인 OS!

### Ubuntu

개인적용도로 가장 접근성이 좋음

{% hint style="info" %}
Cent Os, Amazon Linux, Ubuntu, Debian, Etc ...

목적에 맞는 Linux를 사용하는것이 중요하다.  
\(가장 좋은 Linux는 목적에 맞는 linux!\)
{% endhint %}


# SSH(Secure shell)
- 다른 컴퓨터에 접속하거나 원격 시스템에서 명령을 실행 할 수 있는 클라이언트 / 프로토콜을 의미
- 대부분의 리눅스 배포판에선 기본적으로 설치되어 있음
- 22번 포트 사용
- `-i`옵션으로 비밀번호가 아닌 SSH key로 접속

## SSH Key
- 비밀번호 보다 노은 수준의 보안을 필요할 때 사용
- 서버에 저장 된 Public key와 사용자의 Private key를 비교하여 확인됬을 때만 접속을 허용!

# Web Server
- HTTP 요청을 받고 응답하는 역할을 함
- HTTP transaction을 처리하고 정적인 파일(static file - HTML, CSS , Image 등)을 요청한 대상에게 보내준다.
- Application logic 을 직접 처리 할 수 없어 WAS(Web application server)와 같이 사용한다.
- 대표적으로 Apache, NginX 와 같은 제품이 있다.

## NginX
- Web server software
- Apache Http의 한계를 극복하기 위해 나옴
- 동시 접속 10,0000개 당 평균 memory 접유율 2.5 mb

# WAS(Web Application Server)
- 동적으로 데이터를 생성하여 응답하는 서버
- Application(code) logic을 직접 실행하는 서버(JSP, Java, etc...)
- Tomcat, jBoss, WSGI 등
- 개발하고 있는 언어와 환경에 맞는 WAS를 구축하는것이 중요!

## Port
- TCP/IP로 접속 시 마지막 종단점
- 클라이언트 실행 시 동적으로 Port 번호가 부여됨
- 해당 인스턴스에서 실행되는 클라이언트의 구분을 위해사용
- 일반적으로 SSH(22번), HTTP(80번), WAS(8080번)을 부여
- 도메인(URL)로 접속 시 기본적으로 80번 포트를 사용(생략 가능)