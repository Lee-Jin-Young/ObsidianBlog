---
날짜: 2023-05-17
사용언어: Java
시험:
  - 프로그래머스 Lv.0
학습정도:
  - 상
정답률: 89
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/181933
tags:
  - IF문
---
|           |                                                                  |
| --------- | ---------------------------------------------------------------- |
| 날짜      | 2023-05-17                                                       |
| 사용 언어 | Java                                                             |
| 문제 유형 | IF문                                                             |
| 정답률    | 89%                                                              |
| 문제 URL  | https://school.programmers.co.kr/learn/courses/30/lessons/181933 |

### 문제

###### 문제 설명

두 정수 `a`, `b`와 boolean 변수 `flag`가 매개변수로 주어질 때, `flag`가 true면 `a` + `b`를 false면 `a` - `b`를 return 하는 solution 함수를 작성해 주세요.

##### 제한사항

- -1,000 ≤ `a`, `b` ≤ 1,000

---

### 나의 풀이

```java
class Solution {
    public int solution(int a, int b, boolean flag) {
        int answer = 0;
        
        answer = flag ? a+b : a-b;
        
        return answer;
    }
}ㅊ
```

### 다른 사람의 풀이

```java

```

---
### 관련개념 학습
