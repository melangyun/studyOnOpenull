---
description: DevOps Curriculum
---

# Curriculum



> 수업 자료 : [https://github.com/yykdev/Devops\_Bootcamp](https://github.com/yykdev/Devops_Bootcamp)

## 1-1 웹 서버 구성

서비스 운영에 기본이 되는 웹 서버를 로컬 환경, 클라우드 환경, 컨테이너 환경에 각각 구축하여 각 환경의 장, 단점 과 전체적인 서버 아키텍쳐에 대한 기본 지식을 습득합니다.

* 리눅스 기본 명령어 및 사용 방법
* 운영 모니털이 시 지표 확인에 도움될 정보
* VIM 사용 방법 : vim 기본 명령 \( 검색/ 치환/ 구간복사, 잘라내기 등의 편집 기능\)
* 로컬 환경에서 Nginx 설치
* Docker 설치, Docker hub를 통해 컨테이너 기반의 Nginx설치
* AWS EC2 인스턴스 생성 후 해당 환경에서 Nginx를 설치하여 외부에서 접속



## 1-2. 서버 아키텍처와 컨테이너 환경

모든 상황을 해결하는 하나의 서버 아키텍쳐는 없습니다.  
따라서 각 상황에 맞는 서버 아키텍처를 알아보며, 협업에서는 어떤 방식으로 서버를 운영하는지 다양한 사례들을 살펴봅니다.

**서버 아키텍처 비교**

* 모노리틱 아키텍처
* 서버리스 아키텍처
* 마이크로 서비스 아키텍처

**Docker 이해**

* Docker 개념 및 역사
* Linux 컨테이너 기술에 대한 개념

## 2-1. 다중 서버 환경 구성

실제 운영환경에서는 하나의 서버로 운영할 수 없습니다. 왜냐하면 하나의 서버에 장애가 생길 수도 있고, 트래픽이 너무 많아질 수도 있기 때문입니다. 따라서 서버에 문제가 생기거나 트래픽이 몰려도 장애가 없는 서버를 구성하는 방법을 배웁니다.

1. AWS ELB를 활용하여 로드밸런싱 환경 구축
2. AWS Auto Scaling Group을 통한 다중 서버 구성
3. Faliover 아키텍처 구

## 2-2. 네트워크 기본

서버를 운영하며 알아야 할 기초적인 네트워크 지식을 짚고 삽니다.

1. 포트 포워딩
2. 네트워크 기본
3. 가용성

## 3-1. 웹서버 + WAS + DB서버 - 간이 운영 환경 구축

전체적인 서버 아키텍처로 부터 서버 내부, 외부 등 운영서버에 필요한 요소들을 배우고 구성하게 됩니다. 이 수업이 끝나면 내가 작성한 코드를 운영 환경에서 서비스 할 수 있게 됩니다.

* Nginx
* SSL 설정 및 Multi site
* WAS 프로젝트 간단 소개 \( Node.js\) 및 EC2에서 환경 구축
* AWS  RDS를 통한 DB 서버 구축 \(MYSQL\)
* 간이 인프라\(웹서버 + WAS + DB서버\) 를 구축해보고 통합 테스트

## 3-2. DevOps 로 넘어가기

함께 운영 환경을 구축해보며 어떠한 요소가 더 필요한지 고민해보고 해당 운영 스택을 기반으로 DevOps로 확장할 준비를 합니다.

* 해당 니프라 구축 경험을 다 함께 공유하여 앞으로 어떤 기증이 있으면 좋은지에 대하여 토론하고 AWS제품, 오픈 소스 툴 등을 리서치 해보기
* 모니터링 등
* CI/ CD
* VM환경에서의 한계와 컨테이너 환경

## 4-1. CI/CD, 모니터링 환경 구성

사람은 무조건 실수를 하기 대문에 단순 반복적인 업무는 최대한 기계에 맡겨야 합니다. 코딩 이후 배포까지 필요한 수많은 작업들을 어떻게 자동화하는지 배웁니다.

* AWS 내 사용 빈도가 높은 서비스 제품 소개
* AWS Cloudwatch를 구성하여 모니터링
* Jenkins를 활용한 CI/CD 파이프 라인 구축

## 4-2. CI/CD, 모니터링 환경 구성

대량의 로그를 관리하는 방법과 로그에서 장애의 단서를 재빠르게 찾기 위해 사용되는 시스템의 활용 방법을 배웁니다.  
또한 자동화된 서버 관리에 필요한 요소를 공유합니다.

* 모니터링의 이해와 여러 운영 데이터를 보며 가용성, 병목화 등 운영 경험 공유
* CI/CD의 이해와 배포 전략 및 정책에 대한 경험 공유

## 5~6. 컨테이너 환경으로 이전

**1 ~4주차에 구축한 인프라 환경을 컨테이너 환경으로 이전, 구축하기**

Docekr file 작성/ 빌드, 컨테이너 운영하기

* Docker 명령어
* Docker file작성

AWS ECS를 활용한 Container orchestratin

* AWS ECR에 n개의 Docker file push
* EC n대를 구성 한 후 ECR\(docker file\_을 기반으로 ECS로 클러스터링
* 작업 정의 구성
* 컨테이너 별 포트 매핑
* 컨테이너 Metric\(시스템 자원\) 배치

**AWS ALB\(Aplication load balancer\)를 활용한 컨테이너 로드 밸런싱**

AWS Codepipeline을 활용한 CI/CD

* Github wehook설정
* 컨테이너 별 자동 배치를 위한 Dockerfile재작성
* AWS Codebuild를 통한 자동빌드\(Docker\)설정
* Codepipeline + codevuild + ECS를 활용한 무중단\(블루-그린\)배포

## 7. 서버리스 아키텍처 구축

AWS에서 제공하는 다양한 컴퓨팅 리소스를 활용하여 서버리스 아키텍쳐를 구축해보녀서 기존 아키텍쳐와의 장단점을 비교하여 효율적으로 활용할 수 있는 방안에 대하여 고민합니다.

* AWS S3 + AWS CloudFront CDN 정적 파일 전송 아키텍처 구축
* AWS API Gateway + AWS Lamda + AWS Dynamo DB 웹 서비스 구동을 위한 서버리스 아키텍처 구축
* 다양한 AWS Computing service알아보기

## 8. 컨테이너 오케스트레이션

수 백, 수 천 대의 컨테이너를 쉽게 관리하고 배포하기 위한 다양한 Container orchestraition tool 들에 대해 알아봅시다.

**Docekr swarm Kubernetes**

* AWS EC2\(VM\) 수 십개의 노드를 클러스터링 진행 - Container management tool
* Treafik : Container reverse proxy & load balancer
* Portainer : Swarm management tool Container moniotoring : 모든 Node에 배포된 전체 컨테이너 모니터링
* ELK Stack
* Elasticsearch
* Logstash
* Kibana
* Beats\(Filebeat, Metricbeat\)

