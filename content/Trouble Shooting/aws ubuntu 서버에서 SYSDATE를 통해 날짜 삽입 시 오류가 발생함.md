---
tags: server, ORACLE
상태: true
작성일: 2023년 8월 29일 오후 2:18
---
### 발생한 문제
---

SYSDATE를 DATE열에 넣을 때나 TO_CHAR을 통해 VARCHAR2열에 넣을 때 아래와 같은 오류 발생

ORA-01861: literal does not match format string

### 문제의 일반적인 원인

서버 상에서 LANGUAGE가 AMERICAN으로 잡혀있어 오류발생

문제 해결 방법 요약

1. 값을 넣을 때 포메팅 작업 후 넣는다.
TO_CHAR([날짜 데이터], [문자형태], [NLS_DATE_LANGUAGE = ‘언어’])
    1. TO_CHAR(SYSDATE, ‘YY/MM/DD’, ‘NLS_DATE_LANGUATE = KOREAN’)값으로 설정 시에도 오류발생

### 문제의 일반적인 원인 2

SYSDATE가 DD-MON-RR형태로 반환되어서 기존 db에 넣을 때 구조가 달라 오류가 발생 하였다.

1. DB의 설정에서 SYSDATE를 RR/MM/DD형태로 반환하도록 한다.
ALTER SESSION SET NLS_DATE_FORMAT = ‘RR/MM/DD’;
    1. 해당 기능으로 테스트 중 COMMIT 이슈로 DB LOCK 발생
2. **mapper 작성 시 TO_CHAR, TO_DATE를 이용해 모든 환경에서 동일한 형식을 이용할 수 있도록 한다.**

[https://tyrionlife.tistory.com/28](https://tyrionlife.tistory.com/28)