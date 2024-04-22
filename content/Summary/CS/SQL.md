---
tags: ComputerScience, DataBase
---
**DDL** 데이터 **정의**어 : **스키마**를 **정의**하거나 **수정**, **삭제**
**DML** 데이터 **조작**어 : **데이터**의 **삽입**, **삭제**, **수정**, **검색**등의 처리
**DCL** 데이터 **제어**어 : **데이터베이스**에 **접근** 및 **권한**을 주거나 회수
**TCL** **트랜잭션** 제어어 : **DML**에 의한 **결과**를 **트랜잭션** 별로 **제어**

DDL **Data Definition Language**
    **CREATE** : 스키마/테이블 생성
    **ALTER** : 스키마/테이블 수정
    **DROP** : 스키마/테이블 삭제
    **RENAME** : 테이블 명 수정
    **TRUNCATE** : 스키마/테이블 초기화
****

DML **Data Manipulation Language**
    **SELECT** : 데이터 출력/검색
    **INSERT** : 데이터 삽입
    **UPDATE** : 데이터 갱신
    **DELETE** : 데이터 삭제
****

DCL **Data Control Language**
    **GRANT** : 권한 부여
    **REVOKE** : 권한 회수
****

TCL **Transaction Control Language**
    **COMMIT** : 트랜잭션의 작업 저장
    **ROLLBACK** : 트랜잭션의 작업 취소 및 복구
    SAVEPOINT

---

관계 대수
순수 관계 연산자
    SELECT 행 단위 추출 ⇒ WHERE deptno = 10
    Project 열 단위 추출 / 중복은 제거된다. ⇒ SELECT deptno
    Join
    Division
일반 집합 연산자
    UNION ⇒ 
    INTERSECTION
    DIFFERENCE
    CARTESIAN PRODUCT