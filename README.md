## 프로젝트 개요

`Cloud Native Spring App`은 *Cloud Native Spring in Action* 책을 기반으로 클라우드 네이티브 환경과 MSA(Microservices Architecture) 환경을 이해하고 학습하기 위해 개발된 개인 프로젝트입니다. 마이크로서비스 아키텍처를 활용하여 확장 가능하고 유연한 북스토어 시스템을 구현하였으며, Docker와 Kubernetes를 사용하여 클라우드 환경에서의 배포와 관리, 확장 가능하고 유연한 시스템 구축을 목표로 합니다.

## 프로젝트 구조

### PolarBookshop 아키텍처

![Image](https://github.com/user-attachments/assets/5d33bab2-5516-4063-988b-1228f9e5515c)

## 리포지토리 구성 및 설명

### 1. Edge Service
- **역할**: API Gateway로 동작하며, 클라이언트 요청을 라우팅
- **주요 기술**: 
  - Spring Cloud Gateway
  - Resilience4j (Circuit Breaker)
  - Spring Security
  - KeyCloak
- **주요 기능**:
  - 라우팅 및 로드 밸런싱
  - 서킷 브레이커 패턴 구현
  - 인증/인가
  
### 2. Order Service
- **역할**: 주문 생성, 조회 및 관리
- **주요 기술**:
  - Spring Boot
  - Spring Data R2DBC
  - PostgreSQL
  - Spring WebFlux
  - Spring Cloud Stream (RabbitMQ)
- **주요 기능**:
  - 주문 CRUD 작업
  - 재고 확인 및 관리
  - 주문 상태 추적
  
### 3. Dispatcher Service
- **역할**: 주문 처리 후 배송 관리
- **주요 기술**:
  - Spring Boot
  - RabbitMQ
  - Spring Cloud Stream
- **주요 기능**:
  - 실시간 배송 상태 업데이트
  - 비동기 메시지 처리

### 4. Catalog Service
- **역할**: 서적 관리리
- **주요 기술**:
  - Spring Boot
  - Spring Data JPA
  - PostgreSQL
- **주요 기능**:
  - 상품 CRUD 작업

### 5. Config Service
- **역할**: 마이크로서비스들의 중앙 설정 관리
- **주요 기술**:
  - Spring Cloud Config
  - Git
- **주요 기능**:
  - 환경별 설정 관리
  - 동적 설정 업데이트

## 기술 스택 상세

### Backend
- Java 17
- Spring Boot 3.x
- Spring Cloud 2021.0.x
- Spring Security
- Spring Data JPA
- Spring Cloud Stream

### Database & Cache
- PostgreSQL 14.12
- Redis 7.2
- Flyway (Database Migration)

### Message Queue
- RabbitMQ 3.13

### DevOps & Infrastructure
- Docker
- Kubernetes
- GitHub Actions (CI/CD)
- Grafana, Loki, Fluent Bit (모니터링)

## Project Repository
각 서비스별 소스 코드는 아래 리포지토리에서 확인할 수 있습니다 :D  

- [Edge Service](https://github.com/cordingkid/edge-service)
- [Catalog Service](https://github.com/cordingkid/catalog-service)  
- [Order Service](https://github.com/cordingkid/order-service)  
- [Dispatcher Service](https://github.com/cordingkid/dispatcher-service)
- [Polar Deployment](https://github.com/cordingkid/polar-deployment)
- [Config Service](https://github.com/cordingkid/config-service)  
- [Config Repo](https://github.com/cordingkid/config-repo)  


