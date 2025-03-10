# 자동차 도장 공정 MES 

## 프로젝트 배경

자동차 도장 공정에서 도료 수위, 베이킹 과정, 도장 품질 등을 수작업이나 단순 센서 모니터링 방식으로 관리하고 있어, 다음과 같은 문제점이 발생함
* 도료 수위 부족으로 인한 **불균일한 도장** 문제
* 베이킹 온도 및 습도 변화로 인해 페인트 접착력 저하
* 도장 색상이 원하는 기준과 다르게 나오는 문제
* 센서 데이터를 **통합, 관리**하는 시스템의 부재

## PaintFlow의 솔루션

1. 센서를 수집, 처리하고 PLC 제어를 담당하는 Broker 도입
2. WPF를 통한 실시간 데이터 모니터링 기능
3. 데이터 기반의 공정 최적화

## 프로젝트 목표

> 이 프로젝트는 자동차 도장 공정을 실시간 모니터링을 통해 자동화하여 불량률을 줄이고 생산성을 향상시키는 것을 목표로 합니다. 

## 시스템 아키텍처 (통합)

![1](/img/systemArchitecture.png)


### 사용 기술

하드웨어

* PLC(LS 산전)
* 라즈베리파이(Broker 서버, DB 서버)

소프트웨어

* WPF(.NET 8.0), LiveCharts, Prism, OpenCV(OpenSharp)
* Springboot, Apache Tomcat, Java
* C# Console 앱

KDT 스마트팩토리 단기 심화 3기

* <a href = "https://github.com/salt338-03">김창헌</a>
* <a href = "https://github.com/Kim-yerin0904">김예린 </a>
* <a href = "https://github.com/hyeyeoung">김혜영 </a>
* <a href = "https://github.com/Ahyun-Song">송아현</a>
* <a href = "https://github.com/rninji24">박민지</a>
* <a href = "https://github.com/YoungJunBAS">안영준 </a>

