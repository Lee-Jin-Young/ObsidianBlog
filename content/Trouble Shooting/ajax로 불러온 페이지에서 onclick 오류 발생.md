---
tags:
  - FrontEnd
  - JQuery
상태: true
작성일: 2023년 9월 6일 오전 10:56
---
## 목차

- [[발생한 문제]]
- [[해결 방법 1]]

## 발생한 문제

---

ajax를 통해 다른 페이지를 불러왔을 경우 해당 페이지 내에서 `$(”.class-name”).on(”click”, function(e) { });`형태로 작성 시 함수가 실행 되지 않는 현상 발생

### 문제의 일반적인 원인

요소가 페이지에 **동적으로 추가**되거나 **동적으로 추가된 컨테이너 내에 있는 경우** 이벤트 위임 (Event Delegation)을 통해 이벤트를 추가할 요소를 정확하게 지정 할 필요가 있다.

1. `$(document).on("click", ".class-name", function(e) { });` 형태로 작성하여 새로 불러온 document 내부의 `class = “class-name”`인 요소에 click 이벤트를 부여한다고 정확히 지정한다.