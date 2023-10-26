---
날짜: 2023-10-26
사용언어: Java
시험:
  - 프로그래머스 Lv.0
학습정도:
  - 상
정답률: 89
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/181834
tags:
  - String
  - StringBuffer
---
|           |                                                                  |
| --------- | ---------------------------------------------------------------- |
| 날짜      | 2023-10-26                                                       | 
| 사용 언어 | Java                                                             |
| 문제 유형 | String, String Buffer                                            |
| 정답률    | 89%                                                              |
| 문제 URL  | https://school.programmers.co.kr/learn/courses/30/lessons/181834 |

### 문제

###### 문제 설명

알파벳 소문자로 이루어진 문자열 `myString`이 주어집니다. 알파벳 순서에서 "l"보다 앞서는 모든 문자를 "l"로 바꾼 문자열을 return 하는 solution 함수를 완성해 주세요.

##### 제한사항

- 1 ≤ `myString` ≤ 100,000
    - `myString`은 알파벳 소문자로 이루어진 문자열입니다.

---

### 나의 풀이

```java
class Solution {
    public String solution(String myString) {
        StringBuilder sb = new StringBuilder();
        
        for(char c : myString.toCharArray()) {
            if(c<'l') sb.append("l");
            else sb.append(c);
        }

        return sb.toString();
    }
}
```

### 다른 사람의 풀이

```java
class Solution {
    public String solution(String myString) {
        return myString.replaceAll("[^l-z]", "l");
    }
}
```

---
### 관련개념 학습
[String](Summary/String.md)

[StringBuilder / StringBuffer](Summary/StringBuilder%20Buffer.md)
[StringBuilder / StringBuffer](Summary/StringBuilder Buffer.md)