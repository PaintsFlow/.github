# PaintFlow: 자동차 도장 공정 MES 시스템

## 🚗 프로젝트 개요

자동차 도장 공정은 도장 품질과 생산성에 직결되는 중요한 제조 프로세스입니다. 기존 공정은 분리되어 운영되고 있어, 실시간 데이터 기반의 품질 관리 및 공정 최정화가 어려운 실정입니다. 본 프로젝트는 통합된 제어 시스템을 구축하여 **데이터 수집 최적화 및 모듈 제어 자동화 구현**을 목표로 합니다. 또한, 알람 시스템을 도입하여 획일화된 도장 공정 환경 조성과 OpenCV를 활용한 육안 품질 검사 효율화로 생산성 향상를 기대할 수 있습니다.

본 프로젝트는 가상의 시뮬레이션 환경을 기반으로 수행되었으며, 실환경에서의 센서 데이터 수집이 어려운 경우에는 가상 데이터를 자동 생성하여 분석을 진행하였습니다. 이를 통해 도장 공정의 실시간 데이터 통합 관리 및 최적화 방안을 검증하고, 향후 실제 제조 현장에 적용 가능한 통합 제어 시스템의 프로토타입을 제시하는 데 중점을 두었습니다.

### 문제점 및 해결 과제

* 공정 변수 실시간 최적화 요구 : 전착 도장 공정에서 도료의 수위 및 규질성 유지를 위한 환경 실시간 모니터링의 중요성 상승
* 데이터 통합 부재 : 공정 중 제품의 상품성을 위해 센서 데이터를 종합적으로 관리하는 시스템의 수요 증대

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

## PLC 제어 시뮬레이션

![simul](/img//PLC레더%20움짤.gif)

가상 데이터에 따라 PLC 내부에서 자체적인 프로세스가 수행됩니다.

## 시스템 아키텍처 (통합)

![1](/img/systemArchitecture.png)

## 시스템 아키텍처 (Broker)

![2](/img/차량도장공정-페이지-8.drawio.png)

PLC와 Application들의 중계자로 라즈베리파이 서버에 각 프로그램이 도커 컨테이너로 구동 중 입니다. 
PLC에서 전송받은 데이터를 Application으로 Publish 전, 센서 데이터에 대한 임계치 검사를 진행합니다. 만약, 임계치에 도달한 경우엔 알람을 발생하여 Application으로 Publish합니다.

## ERD

![3](/img/차량도장공정-페이지-9.drawio.png)

* 센서 정보 : paint, dry, electroDeposition
* 품질 검사 정보 : color, product
* 알람 정보 : alarm

## 사용 기술

* C#
    * .Net 6.0 : <a href = "https://github.com/PaintsFlow/prdocer">producer</a>, <a href = "https://github.com/PaintsFlow/Virtual2PLC">Virtual2PLC</a>

    * .Net 8.0 : <a href = "https://github.com/PaintsFlow/CarPaintingProcess">WPF</a>
    * .Net 9.0 : <a href = "https://github.com/PaintsFlow/plccontrol">PlcControl</a>, <a href = "https://github.com/PaintsFlow/InsertDB_App">Insert DB</a>

* Network Protocols
    * Rabbit MQ
    * PLC modbus
    * WEB Soket

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
