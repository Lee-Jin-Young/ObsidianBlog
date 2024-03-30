---
tags: CodingTest
---
| return       | method                                                         | 설명                                           |
| ------------ | -------------------------------------------------------------- | -------------------------------------------- |
| void         | `append(boolean b)`                                            | 불리언 인수의 문자열 표현을 시퀀스에 추가                      |
| void         | `append(char c)`                                               | 문자 인수의 문자열 표현을 시퀀스에 추가                       |
| void         | `append(char[] str)`                                           | 문자 배열 인수의 문자열 표현을 시퀀스에 추가                    |
| void         | `append(char[] str, int offset, int len)`                      | 문자 배열 인수의 하위 배열의 문자열 표현을 시퀀스에 추가             |
| void         | `append(CharSequence s)`                                       | 지정된 CharSequence를 시퀀스에 추가                    |
| void         | `append(CharSequence s, int start, int end)`                   | 지정된 CharSequence의 하위 시퀀스를 시퀀스에 추가            |
| void         | `append(double d)`                                             | double 인수의 문자열 표현을 시퀀스에 추가                   |
| void         | `append(float f)`                                              | float 인수의 문자열 표현을 시퀀스에 추가                    |
| void         | `append(int i)`                                                | int 인수의 문자열 표현을 시퀀스에 추가                      |
| void         | `append(long lng)`                                             | long 인수의 문자열 표현을 시퀀스에 추가                     |
| void         | `append(Object obj)`                                           | 객체 인수의 문자열 표현을 시퀀스에 추가                       |
| void         | `append(String str)`                                           | 지정된 문자열을 시퀀스에 추가                             |
| void         | `append(StringBuffer sb)`                                      | 지정된 StringBuffer를 시퀀스에 추가                    |
| void         | `appendCodePoint(int codePoint)`                               | codePoint 인수의 문자열 표현을 시퀀스에 추가                |
| int          | `capacity()`                                                   | 현재 용량을 반환                                    |
| char         | `charAt(int index)`                                            | 지정된 인덱스의 문자를 반환                              |
| int          | `codePointAt(int index)`                                       | 지정된 인덱스의 문자(유니코드 코드 포인트)를 반환                 |
| int          | `codePointBefore(int index)`                                   | 지정된 인덱스의 이전 문자(유니코드 코드 포인트)를 반환              |
| int          | `codePointCount(int beginIndex, int endIndex)`                 | 지정된 텍스트 범위의 유니코드 코드 포인트 수를 반환                |
| void         | `delete(int start, int end)`                                   | 이 시퀀스의 하위 문자열을 제거                            |
| void         | `deleteCharAt(int index)`                                      | 지정된 위치의 문자를 제거                               |
| void         | `ensureCapacity(int minimumCapacity)`                          | 용량이 최소 지정 용량과 적어도 같도록 보장                     |
| void         | `getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)` | 이 시퀀스에서 대상 문자 배열로 문자를 복사                     |
| int          | `indexOf(String str)`                                          | 지정된 부분 문자열의 첫 번째 발생 위치를 반환                   |
| int          | `indexOf(String str, int fromIndex)`                           | 지정된 문자열의 시작 인덱스부터 지정된 문자열의 첫 번째 발생 위치를 반환    |
| void         | `insert(int offset, boolean b)`                                | 불리언 인수의 문자열 표현을 시퀀스에 삽입                      |
| void         | `insert(int offset, char c)`                                   | 문자 인수의 문자열 표현을 시퀀스에 삽입                       |
| void         | `insert(int offset, char[] str)`                               | 문자 배열 인수의 문자열 표현을 시퀀스에 삽입                    |
| void         | `insert(int index, char[] str, int offset, int len)`           | 문자 배열 인수의 하위 배열의 문자열 표현을 시퀀스에 삽입             |
| void         | `insert(int dstOffset, CharSequence s)`                        | 지정된 CharSequence를 시퀀스에 삽입                    |
| void         | `insert(int dstOffset, CharSequence s, int start, int end)`    | 지정된 CharSequence의 하위 시퀀스를 시퀀스에 삽입            |
| void         | `insert(int offset, double d)`                                 | double 인수의 문자열 표현을 시퀀스에 삽입                   |
| void         | `insert(int offset, float f)`                                  | float 인수의 문자열 표현을 시퀀스에 삽입                    |
| void         | `insert(int offset, int i)`                                    | int 인수의 문자열 표현을 시퀀스에 삽입                      |
| void         | `insert(int offset, long l)`                                   | long 인수의 문자열 표현을 시퀀스에 삽입                     |
| void         | `insert(int offset, Object obj)`                               | 객체 인수의 문자열 표현을 시퀀스에 삽입                       |
| void         | `insert(int offset, String str)`                               | 지정된 문자열을 시퀀스에 삽입                             |
| int          | `lastIndexOf(String str)`                                      | 지정된 부분 문자열의 마지막 발생 위치를 반환                    |
| int          | `lastIndexOf(String str, int fromIndex)`                       | 지정된 문자열의 시작 인덱스부터 지정된 문자열의 마지막 발생 위치를 반환     |
| int          | `length()`                                                     | 길이(문자 수)를 반환                                 |
| int          | `offsetByCodePoints(int index, int codePointOffset)`           | 주어진 인덱스에서 codePointOffset 만큼 이동한 위치의 인덱스를 반환 |
| StringBuffer | `replace(int start, int end, String str)`                      | 이 시퀀스의 하위 문자열을 지정된 문자열로 대체                   |
| StringBuffer | `reverse()`                                                    | 이 시퀀스의 역순으로 대체됩니다.                           |
| void         | `setCharAt(int index, char ch)`                                | 지정된 인덱스의 문자를 지정된 문자로 설정                      |
| void         | `setLength(int newLength)`                                     | 문자 시퀀스의 길이를 설정                               |
| CharSequence | `subSequence(int start, int end)`                              | 이 시퀀스의 하위 시퀀스를 나타내는 새로운 문자열을 반환              |
| String       | `substring(int start)`                                         | 현재 문자 시퀀스에 포함된 문자의 하위 문자열을 반환                |
| String       | `substring(int start, int end)`                                | 현재 문자 시퀀스에 포함된 문자의 하위 문자열을 반환                |
| String       | `toString()`                                                   | 이 시퀀스의 데이터를 나타내는 문자열을 반환                     |
| void         | `trimToSize()`                                                 | 문자 시퀀스에 대한 저장 공간을 최소화                        |
