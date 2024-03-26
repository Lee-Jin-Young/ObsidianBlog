---
날짜: 2023-09-30
시험:
  - 프로그래머스 Lv.0
사용언어: Java
정답률: 66
URL: https://school.programmers.co.kr/learn/courses/30/lessons/120907#
tags:
  - 배열
  - 반복문
  - If문
---
### 문제

덧셈, 뺄셈 수식들이 `'X [연산자] Y = Z'` 형태로 들어있는 문자열 배열 `quiz`가 매개변수로 주어집니다. 수식이 옳다면 "O"를 틀리다면 "X"를 순서대로 담은 배열을 return하도록 solution 함수를 완성해주세요.

##### 제한사항

- 연산 기호와 숫자 사이는 항상 하나의 공백이 존재합니다. 단 음수를 표시하는 마이너스 기호와 숫자 사이에는 공백이 존재하지 않습니다.
- 1 ≤ `quiz`의 길이 ≤ 10
- X, Y, Z는 각각 0부터 9까지 숫자로 이루어진 정수를 의미하며, 각 숫자의 맨 앞에 마이너스 기호가 하나 있을 수 있고 이는 음수를 의미합니다.
- X, Y, Z는 0을 제외하고는 0으로 시작하지 않습니다.
- -10,000 ≤ X, Y ≤ 10,000
- -20,000 ≤ Z ≤ 20,000
- `[연산자]`는 + 와 - 중 하나입니다.

---
### 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public String[] solution(String[] quiz) {
        // 좌항에서 우항을 뺀 결과가 0일경우 좌항과 우항의 값은 동일함을 이용한다.
        String[] answer = new String[quiz.length];
        
        for(int i = 0; i<quiz.length; i++) {
            String[] qu = quiz[i].replaceAll("- ", "-").replaceAll("[+] ", "").replaceAll("[=] ","-").replaceAll("--", "").trim().split(" ");
            answer[i] = Arrays.stream(qu).mapToInt(Integer::parseInt).sum() == 0 ? "O" : "X";
        }
        
        return answer;
    }
}
```

테스트 케이스 1이라면
```
quiz[0].replaceAll("- ", "-")는 "3 -4 = -3"
			 .replaceAll("[+] ", "") 는 "3 -4 = -3"
			 .replaceAll("[=] ","-") 는 "3 -4 --3"
			 .replaceAll("--", "") 는 "3 -4 3"

Arrays.stream(qu).mapToInt(Integer::parseInt)는 [3, -4, 3]
								 .sum() 는 2

따라서 quiz[0]은 "X"
동일한 절차에 따라 quiz[1]은 "O"이므로
quiz는 ["X","O"]
```

### 다른 사람의 풀이

```java
class Solution {
    public String[] solution(String[] quiz) {
        for(int i=0; i<quiz.length; i++){
            String[] text = quiz[i].split(" ");
            int result = Integer.parseInt(text[0]) + ( Integer.parseInt(text[2]) * ( text[1].equals("+") ? 1:-1) );
            quiz[i] = result == Integer.parseInt(text[4])? "O": "X";
        }
        return quiz;
    }
}
```

테스트 케이스 1이라면
```
quiz[0].split(" ") 는 ["3", "-", "4", "=", "-3"]
Integer.parseInt(text[0]) 는 3
Integer.parseInt(text[2]) 는 4
text[1].equals("+") ? 1 : -1 는 -1

result는 3-4 = -1
Integer.parseInt(text[4])는 -3

따라서 quiz[0]은 "X"
동일한 절차에 따라 quiz[1]은 "O"이므로
quiz는 ["X","O"]
```

---
## 관련개념 학습

[Arrays](Summary/Arrays.md)

[문자열 계산하기](문자열%20계산하기.md)