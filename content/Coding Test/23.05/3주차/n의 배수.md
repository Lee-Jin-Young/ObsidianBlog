---
날짜: 2023-05-17
사용언어: Java
시험:
  - 프로그래머스 Lv.0
학습정도:
  - 상
정답률: 89
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/181937
tags:
  - IF문
---
|           |                                                                  |
| --------- | ---------------------------------------------------------------- |
| 날짜      | 2023-05-17                                                       |
| 사용 언어 | Java                                                             |
| 문제 유형 | IF문                                                             |
| 정답률    | 89%                                                              |
| 문제 URL  | https://school.programmers.co.kr/learn/courses/30/lessons/181937 |

### 문제

###### 문제 설명

정수 `num`과 `n`이 매개 변수로 주어질 때, `num`이 `n`의 배수이면 1을 return `n`의 배수가 아니라면 0을 return하도록 solution 함수를 완성해주세요.

##### 제한사항

- 2 ≤ `num` ≤ 100
- 2 ≤ `n` ≤ 9

---

### 나의 풀이

```java
class Solution {
    public int solution(int num, int n) {
        int answer = 0;
        
        answer = num%n==0 ? 1 : 0;
        
        return answer;
    }
}
```

### 다른 사람의 풀이

```java
class Solution {
    public int solution(int num, int n) {
        return num%n==0 ? 1 : 0;
    }
}
```

---
### 관련개념 학습
