---
tags: server
상태: true
작성일: 2023년 9월 7일 오전 8:38
---
### 발생한 문제
---

**502 Bad Gateway** nginx/1.18.0 (Ubuntu)

[error] 449#449: *50 connect() failed (111: Unknown error) while connecting to upstream, client: —, server: bookmate.life, request: "GET /favicon.ico HTTP/1.1", upstream: "[http://127.0.0.1:9000/favicon.ico](http://127.0.0.1:9000/favicon.ico)", host: "bookmate.life", referrer: "[https://bookmate.life/](https://bookmate.life/)"

nohup를 통해 war파일(톰캣서버)를 백그라운드에서 실행했다고 생각했는데 데몬처럼 실행되서 생긴 문제였다.

### 문제의 일반적인 원인

문제 해결 방법 요약

1. `tail -f /var/log/nginx/error.log` 를 통해 로그 확인
    1. “localhost:9000/”의 파일을 불러올 수 없다는 오류
2. `ps -ef | grep "파일명"` 을 통해 파일이 실행 중 인지 확인

### 문제의 일반적인 인 2

문제 해결 방법 요약

1. 해결 방법 단계