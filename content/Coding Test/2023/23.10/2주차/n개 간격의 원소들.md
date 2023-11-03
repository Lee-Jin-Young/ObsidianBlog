---
날짜: 2023-10-10
사용언어: Java
시험:
  - 프로그래머스 Lv.0
학습정도:
  - 상
정답률: 89
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/181888
tags:
  - 배열
  - 반복문
---
|           |                                                                  |
| --------- | ---------------------------------------------------------------- |
| 날짜      | 2023-10-10                                                       |
| 사용 언어 | Java                                                             |
| 문제 유형 | 반복문, 배열                                                     |
| 정답률    | 89%                                                              |
| 문제 URL  | https://school.programmers.co.kr/learn/courses/30/lessons/181888 |

### 문제

###### 문제 설명

정수 리스트 `num_list`와 정수 `n`이 주어질 때, `num_list`의 첫 번째 원소부터 마지막 원소까지 `n`개 간격으로 저장되어있는 원소들을 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

##### 제한사항

- 5 ≤ `num_list`의 길이 ≤ 20
- 1 ≤ `num_list`의 원소 ≤ 9
- 1 ≤ `n` ≤ 4

---

### 나의 풀이

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[(num_list.length-1)/n+1];
        int j = 0;
        
        for(int i = 0; i<num_list.length; i=i+n) {
            answer[j] = num_list[i];
            j++;
        }
        
        return answer;
    }
}
```

### 다른 사람의 풀이

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[num_list.length % n == 0 ? num_list.length / n : num_list.length / n + 1];
        for (int i = 0; i < answer.length; i++) {
            answer[i] = num_list[i * n];
        }
        return answer;
    }

}
```

---
### 관련개념 학습

