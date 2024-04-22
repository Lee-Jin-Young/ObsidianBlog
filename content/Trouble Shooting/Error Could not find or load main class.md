---
tags:
  - server
  - JRE_JDK
상태: true
작성일: 2023년 9월 4일 오후 9:29
---
### 발생한 문제
---

Error: Could not find or load main class Acorn_Team_Project.Soso.target.Soso-0.1.2.war
Caused by: java.lang.ClassNotFoundException: Acorn_Team_Project.Soso.target.Soso-0.1.2.war

메모리 부족으로 인스턴스를 껐다 켠 이후부터 위와 같은 오류 발생

### 문제의 일반적인 원인

java 버전이 맞지 않는 경우가 있다.

1. `java -version` 및 `javac -version` 으로 jre/jdk버전 확인
2. 호환되지 않는 버전일 경우 재설치

### 문제의 일반적인 원인 2

%JAVAHOME% 경로 미 설정

1. `nano ~/ .bashrc` 에서