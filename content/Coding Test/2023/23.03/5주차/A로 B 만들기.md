---
날짜: 2023-03-30
시험:
  - 프로그래머스 Lv.0
사용언어: Java
학습정도:
  - 중
문제 URL: https://school.programmers.co.kr/learn/courses/30/lessons/120886
정답률: 85
tags:
  - 배열
  - 문자열
---

## 문제

문자열 `before`와 `after`가 매개변수로 주어질 때, `before`의 순서를 바꾸어 `after`를 만들 수 있으면 1을, 만들 수 없으면 0을 return 하도록 solution 함수를 완성해보세요.

##### 제한사항

- 0 < `before`의 길이 == `after`의 길이 < 1,000
- `before`와 `after`는 모두 소문자로 이루어져 있습니다.

---
## 나의 풀이

```java
import java.util.*;

class Solution {
    public int solution(String before, String after) {
        int answer = 2;
        char[] charBefo = before.toCharArray();
        char[] charAftr = after.toCharArray();
        Arrays.sort(charBefo);
        Arrays.sort(charAftr);
        
        for(int i = 0; i<charBefo.length; i++) {
            if(charBefo[i]==charAftr[i]) {
                answer = 1;
            }
            else {
                answer = 0;
                break;
            }
        }
        
        return answer;
    }
}
```

```java
import java.util.*;

class Solution {
    public int solution(String before, String after) {
        int answer = 2;
        char[] charBefo = before.toCharArray();
        char[] charAftr = after.toCharArray();
        Arrays.sort(charBefo);
        Arrays.sort(charAftr);
        
        before = String.valueOf(charBefo);
        after = String.valueOf(charAftr);
        
        answer = before.equals(after) == true? 1 : 0;
        return answer;
    }
}
```

- before와 after를 정렬한 후 비교하여 동일하면 before의 순서를 바꾸어 after를 만들 수 있음을 이용한다.
- String은 정렬이 불가능함으로 charArray의 형태로 바꾸어 정렬한다.
- 정렬 후 비교하여 같다면 1을 다르면 0을 return한다.
    - String형태로 다시 변환후 equls()를 이용한다.
    - 반복문을 이용하여 각 배열을 비교한다.

## 다른 사람의 풀이

```java
import java.util.Arrays;
class Solution {
    public int solution(String before, String after) {
        char[] a = before.toCharArray();
        char[] b = after.toCharArray();
        Arrays.sort(a);
        Arrays.sort(b);

        return new String(a).equals(new String(b)) ? 1 :0;
    }
}
```

- char[] to String변환 시 new String을 이용하여 더 간략히 표현하였다.

---
## 관련개념 학습

[String](String.md)

[Arrays](Arrays.md)