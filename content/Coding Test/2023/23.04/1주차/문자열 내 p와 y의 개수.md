---
title: 문자열 내 p와 y의 개수
날짜: 2023-04-04
시험: 프로그래머스 Lv.1
사용언어: Java
학습정도: 중
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/12916
---
## 문제

대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

- 제한사항
    - 문자열 s의 길이 : 50 이하의 자연수
    - 문자열 s는 알파벳으로만 이루어져 있습니다.
- 입출력 예
    
    
    | s | answer |
    | --- | --- |
    | "pPoooyY" | true |
    | "Pyy" | false |

## 나의 풀이

```java
class Solution {
    boolean solution(String s) {
        boolean answer = true;
        
        s = s.toLowerCase();
        String p = s.replace("p","");
        String y = s.replace("y","");
        answer = p.length() == y.length() ? true : false;

        // [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
        System.out.println(answer);

        return answer;
    }
}
```

## 다른 사람의 풀이

```java
class Solution {
    boolean solution(String s) {
        s = s.toLowerCase();
        int count = 0;

        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == 'p')
                count++;
            else if (s.charAt(i) == 'y')
                count--;
        }

        return count == 0;
    }
}
```

## 관련개념 학습

-