---
title: k의 개수
날짜: 2023-03-31
시험: 프로그래머스 Lv.0
사용언어: Java
학습정도: 중
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/120887
---
## 문제

1부터 13까지의 수에서, 1은 1, 10, 11, 12, 13 이렇게 총 6번 등장합니다. 정수 `i`, `j`, `k`가 매개변수로 주어질 때, `i`부터 `j`까지 `k`가 몇 번 등장하는지 return 하도록 solution 함수를 완성해주세요.

- 제한사항
    - 1 ≤ `i` < `j` ≤ 100,000
    - 0 ≤ `k` ≤ 9
- 입출력 예
    
    
    | i | j | k | result |
    | --- | --- | --- | --- |
    | 1 | 13 | 1 | 6 |
    | 10 | 50 | 5 | 5 |
    | 3 | 10 | 2 | 0 |

## 나의 풀이

```java
class Solution {
    public int solution(int i, int j, int k) {
        int answer = 0;
        String num = "";
        for(int l = i; l <= j; l++){
            num += l;
        }
        String[] numArr = num.split("");

        for(int m = 0; m < num.length(); m++){
            if(numArr[m].equals(String.valueOf(k)))
                answer++;
        }
        
        return answer;
    }
}
```

- 코드 해설을 적는다.

## 다른 사람의 풀이

```java
class Solution {
    public int solution(int i, int j, int k) {
        int answer = 0;

        for (int num = i; num <= j; num++){
            int tmp = num;
            while (tmp != 0){
                if (tmp % 10 == k)
                    answer++;
                tmp /= 10;
            }
        }
        return answer;
    }
}
```

- 각 숫자별로 자릿수마다 k와 동일한지 판별 후 동일하다면 카운트 하는 방식을 이용하였다.

```java
class Solution {
    public int solution(int i, int j, int k) {
        String str = "";
        for(int a = i; a <= j; a++) {
            str += a+"";
        }

        return str.length() - str.replace(k+"", "").length();
    }
}
```

- 문자열에서 `replace`를 이용해 k를 지우고 이전 문자열의 길이에서 삭제후 길이를 뺌으로써 k의 갯수를 구하였다.
- `str.replace(k+"", "")` 에서`k+""`는 int형인 `k`를 String형으로 바꾸어준다.

## 관련개념 학습

- 관련 개념을 찾아서 공부한 내용을 적는다.
- `ctrl + p`로 내가 필기한 내용 중에서 관련내용이 있는지 찾아서 그 페이지의 링크를 복사하여 붙혀넣는다.
- 필기 페이지에도 이 문제의 링크를 복사하여 "관련 문제"라고 써놓고 붙혀넣는다.