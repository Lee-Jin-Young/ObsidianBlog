---
tags:
  - CodingTest
---
| return        | method                                      | 설명                                                                          |
| ------------- | ------------------------------------------- | ----------------------------------------------------------------------------- |
| int           | `CharAt(int index)`                         | 문자열의 index번째 Char값을 반환                                              |
| String        | `concat(String str)`                        | 문자열의 끝에 str을 이어붙인값을 반환                                         |
| boolean       | `contains(CharSequence s)`                  | 문자열에 s가 포함된 경우 true를 반환                                          |
| boolaen       | `endsWith(String suffix)`                   | 문자열이 suffix로 끝날 경우 true를 반환                                       |
| boolean       | `equals(Object anObject)`                   | 문자열이 anObject와 동일할 경우 true를 반환                                   |
| int           | `indexOf(String str)`                       | 문자열 내부에서 str이 처음 나타나는 인덱스를 반환                             |
| int           | `lastIndexOf(String str)`                   | 문자열 내부에서 str가 마지막으로 나타나는 인덱스를 반환                       |
| int           | `length()`                                  | 문자열의 길이를 반환                                                          |
| boolean       | `matches(String regex)`                     | 문자열이 주어진 정규식 regex와 일치할 경우 true 반환                          |
| String        | `replace(char oldChar, char newChar)`       | 문자열 내부의 oldChar을 newChar로 변경                                        |
| String        | `replaceAll(String regex, String newStr)`   | 문자열 내부에서 주어진 정규식regex와 일치하는 모든 문자열을 newStr로 변경     |
| String        | `replaceFirst(String regex, String newStr)` | 문자열 내부에서 주어진 정규식(regex)와 일치하는 첫번째 문자열을 newStr로 변경 |
| String`[]`    | `split(String regex)`                       | 주어진 정규식regex를 기준으로 분할한 문자열 배열을 반환                       |
| boolean       | `startsWith(String prefix)`                 | 문자열에 prefix로 시작하는 경우 true를 반환                                   |
| String        | `substring(int beginIndex)`                 | 문자열의 beginIndex부터 반환                                                  |
| String        | `substring(int beginIndex, int endIndex)`   | 문자열의 beginIndex부터 endIndex까지 반환                                     |
| char`[]`      | `toCharArray()                              | 문자열을 문자(Char)배열로 변환                                                |
| String        | `toLowerCase()`                             | 문자열의 모든 문자를 소문자로 변경                                            |
| String        | `toString()`                                | 문자열로 형태 변환하여 반환, `+""`로 대체 가능                                |
| String        | `toUpperCase()`                             | 문자열의 모든 문자를 대문자로 변경                                            |
| String        | `trim()`                                    | my_str의 앞, 뒤 공백을 제거                                                   |
| static String | `valueOf(Object obj)`                       | 매개변수의 문자열 표현을 반환                                                 |

[String (Java Platform SE 8 )](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)