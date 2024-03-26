---
tags: server
상태: 해결 완료
완료: 2023년 8월 21일 → 2023년 8월 22일
---


## 발생한 문제

---

https사용을 위한 ssl설정 중 대상 그룹 중 80, 443은 Health checks failed가 9000번 포트는 Health checks failed with these codes: `[302]`가 발생함

---
### 문제 해결 방법 1
Spring Boot에서 메인 경로가 `/`가 아닌 `/soso`로 설정 되어 있어 생긴 문제로 상태 확인 경로를 변경

### 문제 해결 방법 2
health check설정에서 Success codes가 202로 기본 설정 되어있지만 302를 반환하여 생긴 문제로 Success codes를 302로 변경

### 문제 해결 방법 3
80, 443포트의 경우 상태 검사 유예 기간이 짧아 생긴 문제로 시간을 늘려 해결

---
#### 참고 자료
[aws ELB 헬스체크 실패 이슈](https://velog.io/@suhongkim98/Task-failed-ELB-health-checks-in-target-group-arnawselasticloadbalancingap-northeast-2452444279327targetgroup)