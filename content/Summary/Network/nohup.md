---
tags:
  - Linux
---


[Linux - 백그라운드 실행 nohup 과 & 이해, Python 사용법](https://asecurity.dev/entry/Linux-백그라운드-실행-nohup-과-이해-Python-사용법)

[Linux java -jar 백그라운드 실행(nohup)](https://wlsufld.tistory.com/22)

1. 리눅스 환경에서 java (jar)를 데몬처럼 실행

$ java –jar abcdefg.jar &(사용자가 로그아웃시 프로그램 종료 됨)

2. 사용자가 로그아웃해도 백그라운드로 실행되게 하는 명령어

$ nohup java -jar abcdefg.jar &

3. 프로세스 종료

찾기 : ps –ef | grep 'abcdefg'종료 : kill -9 (pid)

[[Linux] nohup.out 원하는 로그 보기 (tail 명령어)](https://seongbindb.tistory.com/146)

- f: 파일의 마지막 10라인을 실시간으로 계속 출력한다
    - 예) tail -f nohup.out
- n : 원하는 수 라인 만큼 출력한다.
    - 예) tail -n 10 nohup.out (마지막 부터 10줄을 출력한다)
    - 예) tail -n +10 nohup.out (파일의 10번째 줄 이후부터 출력한다)
    - 예 ) **tail -f -n 100 'nohup.out**(마지막 부터 100줄을 실시간으로 출력)
- grep
    - 문서의 특정 패턴이 들어간 라인만 출력한다, 로그 추적에 편리하다
    - 예) tail -f nohup.out | grep "example"
        - 마지막 부터 10줄에 example이 들어간 라인들을 출력한다
    - 예) tail -100f nohup.out | grep "example"
        - 마지막 부터 100줄에 example이 들어간 라인들을 출력한다.