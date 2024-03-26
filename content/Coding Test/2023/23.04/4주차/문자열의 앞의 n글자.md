---
title: 문자열의 앞의 n글자
날짜: 2023-04-24
시험: 프로그래머스 Lv.0
사용언어: Java
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/181907
---
## 문제

문자열 `my_string`과 정수 `n`이 매개변수로 주어질 때, `my_string`의 앞의 `n`글자로 이루어진 문자열을 return 하는 solution 함수를 작성해 주세요.

- 제한사항
    - `my_string`은 숫자와 알파벳으로 이루어져 있습니다.
    - 1 ≤ `my_string`의 길이 ≤ 1,000
    - 1 ≤ `n` ≤ `my_string`의 길이
- 입출력 예
    
    
    | my_string | n | result |
    | --- | --- | --- |
    | "ProgrammerS123" | 11 | "ProgrammerS" |
    | "He110W0r1d" | 5 | "He110" |

## 나의 풀이

```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = my_string.substring(0,n);
        return answer;
    }
}
```

## 다른 사람의 풀이

```java
//다른 사람의 풀이중 참조할 코드를 적는다.
```

## 관련개념 학습

-