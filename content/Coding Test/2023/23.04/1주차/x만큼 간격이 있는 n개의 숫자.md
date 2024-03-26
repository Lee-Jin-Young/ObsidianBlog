---
title: x만큼 간격이 있는 n개의 숫자
날짜: 2023-04-04
시험: 프로그래머스 Lv.1
사용언어: Java
학습정도: 중
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/12954
---
## 문제

함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.

- 제한사항
    - x는 -10000000 이상, 10000000 이하인 정수입니다.
    - n은 1000 이하인 자연수입니다.
- 입출력 예
    
    
    | x | n | answer |
    | --- | --- | --- |
    | 2 | 5 | [2,4,6,8,10] |
    | 4 | 3 | [4,8,12] |
    | -4 | 2 | [-4, -8] |

## 나의 풀이

```java
class Solution {
    public long[] solution(int x, int n) {
        long[] answer = new long[n];
        long sum = x;
        
        for(int i = 0; i<n; i++) {
            answer[i] = sum;
            sum += x;
        }
        
        return answer;
    }
}
```

## 다른 사람의 풀이

```java
class Solution {
    public static long[] solution(int x, int n) {
        long[] answer = new long[n];
        answer[0] = x;

        for (int i = 1; i < n; i++) {
            answer[i] = answer[i - 1] + x;
        }

        return answer;

    }
}
```

## 관련개념 학습

-