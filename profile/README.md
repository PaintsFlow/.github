# PaintFlow: 자동차 도장 공정 MES 시스템

## 🚗 프로젝트 개요

자동차 도장 공정은 도장 품지로가 생산성에 직결되는 중요한 제조 프로세스입니다. 기존 공정이 수작업 및 단순 센서 모니터링 방식으로 운영되고 있어, 실시간 데이터 기반의 품질 관리 및 공정 최적화가 어려운 실정입니다. 본 프로젝트는 **자동화된 데이터 수집 및 분석을 통해 품질을 향상시키고, 생산성을 극대화하는 MES 시스템**을 구축하는 것을 목표로 합니다.

### 문제점 및 해결 과제

* 공정 변수 실시간 최적화 요구: 전착 도장 공정에서 도료의 수위 및 규질성 유지를 위한 환경 실시간 모니터링의 중요성 상승
* 데이터 통합 부재: 공정 중 제품의 상품성을 위해 센서 데이터를 종합적으로 관리하는 시스템의 수요 증대

## PaintFlow의 솔루션

1. 데이터 기반의 실시간 모니터링 시스템 구축
    * 센서 데이터를 수집, 처리 및 통합 관리하는 Broker 도입
    * WPF와 WEB기반의 실시간 공정 모니터링 UI 제공
2. 공정 최적화 및 자동화 시스템 도입
    * PLC와의 연동을 통해 주요 공정 변수를 제어
    * 데이터 분석을 통한 공정 이상 감지 및 예방 조치 수행
3. PLC 자동 제어 시스템 도입
    * 도장 공정 환경 제어를 위한 자동화 시스템 도입
    * 센서 데이터에 따른 적합한 대응 수행

## 프로젝트 목표

자동화 도장 공정의 **실시간 모니터링** 및 **자동화**를 통해 품질을 향상시키고, 불량률을 줄이며, **생산성**을 극대화하는 것을 목표로 합니다.

## 시스템 아키텍처 (통합)

![1](/img/systemArchitecture.png)


## 사용 기술

### 🔨하드웨어

* PLC(LS 산전) : 공정 데이터 수집 및 제어
* 라즈베리파이 : Broker 서버 및 데이터베이스 서버 역할 수행
* 아두이노(수위 센서) : 실물 센서 데이터 수집

### 🖥️소프트웨어

* Frontend(WPF)
    * .NET 8.0 기반 UI 개발
    * LiveCharts, Prism 활용한 데이터 시각화 및 컴포넌트 관리
    * OpenCV(OpenSharp) 적용을 통한 영상 데이터 처리

* Backend(Broker, WEB, DB)
    * Spring Boot, Apache Tomcat, Java 기반 Web 서버 구축
    * C# Console Application을 활용한 Broker 서버 구축
    * MySQL 기반 데이터베이스 구축

#### KDT 스마트팩토리 단기 심화 3기
* <a href = "https://github.com/salt338-03">김창헌</a> (WPF, PLC)
* <a href = "https://github.com/Kim-yerin0904">김예린 </a> (WPF)
* <a href = "https://github.com/hyeyeoung">김혜영 </a> (팀장, Broker)
* <a href = "https://github.com/Ahyun-Song">송아현</a> (WEB)
* <a href = "https://github.com/rninji24">박민지</a> (WEB)
* <a href = "https://github.com/YoungJunBAS">안영준 </a> (PLC)