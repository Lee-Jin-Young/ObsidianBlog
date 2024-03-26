---
날짜: 2023-09-25
사용언어: Java
시험:
  - 프로그래머스 Lv.0
학습정도:
  - 중
정답률: 89
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/181892
tags:
  - 배열
---
|        |                                                                  |
| ------ | ---------------------------------------------------------------- |
| 날짜     | 2023-09-25                                                       |
| 사용 언어  | Java                                                             |
| 문제 유형  | 배열                                                               |
| 정답률    | 89%                                                              |
| 문제 URL | https://school.programmers.co.kr/learn/courses/30/lessons/181892 |

### 문제

###### 문제 설명

정수 리스트 `num_list`와 정수 `n`이 주어질 때, `n` 번째 원소부터 마지막 원소까지의 모든 원소를 담은 리스트를 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

- 2 ≤ `num_list`의 길이 ≤ 30
- 1 ≤ `num_list`의 원소 ≤ 9
- 1 ≤ `n` ≤ `num_list`의 길이

---

### 나의 풀이

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[num_list.length-n+1];
        
        for(int i = 0; i<answer.length; i++) {
            answer[i] = num_list[n+i-1];
        }
        
        return answer;
    }
}
```

### 다른 사람의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] a= Arrays.copyOfRange(num_list, n-1, num_list.length);
        return a;
    }
}
```

---
### 관련개념 학습

[Arrays](Summary/Arrays.md)