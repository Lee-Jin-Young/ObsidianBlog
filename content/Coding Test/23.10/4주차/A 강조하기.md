---
날짜: 2023-10-28
사용언어: Java
시험:
  - 프로그래머스 Lv.0
학습정도:
  - 상
정답률: 89
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/181874
tags:
  - String
---
|           |                                                                  |
| --------- | ---------------------------------------------------------------- |
| 날짜      | 2023-10-28                                                       |
| 사용 언어 | Java                                                             |
| 문제 유형 | String                                                           |
| 정답률    | 89%                                                              |
| 문제 URL  | https://school.programmers.co.kr/learn/courses/30/lessons/181874 |

### 문제

###### 문제 설명

문자열 `myString`이 주어집니다. `myString`에서 알파벳 "a"가 등장하면 전부 "A"로 변환하고, "A"가 아닌 모든 대문자 알파벳은 소문자 알파벳으로 변환하여 return 하는 solution 함수를 완성하세요.

##### 제한사항

- 1 ≤ `myString`의 길이 ≤ 20
    - `myString`은 알파벳으로 이루어진 문자열입니다.

---

### 나의 풀이

```java
class Solution {
    public String solution(String myString) {
        String answer = myString.toLowerCase();
        answer = answer.replaceAll("a", "A");
        return answer;
    }
}
```

### 다른 사람의 풀이

```java
class Solution {
    public String solution(String myString) {
        return myString.toLowerCase().replaceAll("a", "A");
    }
}
```

---
### 관련개념 학습

[String](Summary/String.md)