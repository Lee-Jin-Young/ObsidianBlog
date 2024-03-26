---
title: n의 배수 고르기
날짜: 2023-03-27
시험: 프로그래머스 Lv.0
사용언어: Java
학습정도: 하
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/120905
---
## 문제

정수 `n`과 정수 배열 `numlist`가 매개변수로 주어질 때, `numlist`에서 `n`의 배수가 아닌 수들을 제거한 배열을 return하도록 solution 함수를 완성해주세요.

- 제한사항
    - 1 ≤ `n` ≤ 10,000
    - 1 ≤ `numlist`의 크기 ≤ 100
    - 1 ≤ `numlist`의 원소 ≤ 100,000
- 입출력 예
    
    
    | n | numlist | result |
    | --- | --- | --- |
    | 3 | [4, 5, 6, 7, 8, 9, 10, 11, 12] | [6, 9, 12] |
    | 5 | [1, 9, 3, 10, 13, 5] | [10, 5] |
    | 12 | [2, 100, 120, 600, 12, 12] | [120, 600, 12, 12] |

## 나의 풀이

```java
import java.util.*;

class Solution {
    public int[] solution(int n, int[] numlist) {
        List<Integer> list = new ArrayList<>();
        
        //배수일 경우 리스트에 추가
        for(int i : numlist){
            if(i%n==0){
                list.add(i);
            }
        }
        
        int[] answer = new int[list.size()];
        for (int j = 0; j < list.size(); j++) {
            answer[j] = list.get(j);
        }
        return answer;
    }
}
```

- `numlist` 배열을 반복문으로 돌면서, `n`으로 나누어 떨어지는지 확인한다.
- `numlist` 배열이 `n` 으로 나누어 떨어질 경우, `list`에추가한다.
- `list`에 추가한 후, 해당 `list`를 배열로 변환하여 반환한다.

## 다른 사람의 풀이

```java
class Solution {
    public int[] solution(int n, int[] numlist) {
        int count = 0;
        for(int i : numlist){
            if(i%n==0){
                count++;
            }
        }

        int[] answer = new int[count];
        int idx = 0;
        for(int i : numlist){
            if(i%n==0){
                answer[idx]=i;
                idx++;
            }
        }

        return answer;
    }
}
```

- 배열의 크기를 미리 계산하여 불필요한 `ArrayList` 생성을 피한다.
- 배열 내에서 `n`의 배수가 몇 개인지 계산한다.
- 그 개수만큼의 크기를 가지는 배열을 생성한다.
- 배열 내에서 `n`의 배수를 찾아서 새로 생성한 배열에 저장한다.

## 관련개념 학습

- 관련 개념을 찾아서 공부한 내용을 적는다.
- `ctrl + p`로 내가 필기한 내용 중에서 관련내용이 있는지 찾아서 그 페이지의 링크를 복사하여 붙혀넣는다.
- 필기 페이지에도 이 문제의 링크를 복사하여 "관련 문제"라고 써놓고 붙혀넣는다.