---
title: n번째 원소까지
날짜: 2023-05-17
시험: 프로그래머스 Lv.0
사용언어: Java
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/181889
---
### 문제

정수 리스트 `num_list`와 정수 `n`이 주어질 때, `num_list`의 첫 번째 원소부터 `n` 번째 원소까지의 모든 원소를 담은 리스트를 return하도록 solution 함수를 완성해주세요.

- 제한사항
    - 2 ≤ `num_list`의 길이 ≤ 30
    - 1 ≤ `num_list`의 원소 ≤ 9
    - 1 ≤ `n` ≤ `num_list`의 길이 ___
- 입출력 예
    
    
    | num_list | n | result |
    | --- | --- | --- |
    | [2, 1, 6] | 1 | [2] |
    | [5, 2, 1, 7, 5] | 3 | [5, 2, 1] |
---
### 문제분석

배열을 자르는(split)방법을 아는지 묻는 문제이다.

### 나의 풀이

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[n];
        
        for(int i = 0; i<n; i++) {
            answer[i] = num_list[i];
        }
        
        return answer;
    }
}
```

### 다른 사람의 풀이

```java
//다른 사람의 풀이중 참조할 코드를 적는다.
```

## 관련개념 학습

-