---
개발시작날짜: 2023년 8월 21일
업데이트날짜: 2023년 8월 23일
생성 일시: 2023년 8월 21일 오전 10:18
tags:
  - Linux
---

##코드의 목적 : Why?

- 서버의 보안을 높이기 위해 https 연결을 지원하려고 한다.
    
    

### 코드 아이디어 : How?

1. 사용자가 www.bookmate.life를 주소창에 입력한다.
2. cname 설정을 통해 bookmate.life로 이동
3. bookmate.life에서 ELB 로 이동
4. ELB에서 443(HTTPS)포트를 통해
5. ACM에서 발급 받은 SSL 적용
6. 9000번 포트를 통해 WAS(Spring Boot Tomcat) 으로 이동

---

### 코드를 통해 계산하고자 하는 것 : What?

- 
    
    

---

### 피드백 : Feed back

[HTTPS] 사이트에 보안 연결할 수 없음 

[ELB] unhealthy 

[DNS] 레코드 타입 오류 

---

### 참고자료 출처

elb, acm이용