---
tags:
  - server
  - Nginx
상태: true
작성일: 2023년 9월 11일 오전 10:46
---
### 발생한 문제 
---

웹 사이트 상에서 사진과 같은 파일을 불러 올 때 일부 파일만 불러와지며, 그 외의 파일은 아래와 같은 오류 발생

```bash
2023/09/11 12:00:02 [crit] 8766#8766: *470 open() "/var/lib/nginx/proxy/4/07/0000000074" failed (13: Permission denied) while reading upstream, client: 121.166.197.160, server: bookmate.life, request: "GET /resources/images/main/high-angle-people-reading-together.png HTTP/1.1", upstream: "http://127.0.0.1:9000/resources/images/main/high-angle-people-reading-together.png", host: "bookmate.life", referrer: "https://bookmate.life/resources/css/main.css"
```

```bash
121.166.197.160 - - [11/Sep/2023:12:00:02 +0900] "GET /resources/images/main/high-angle-people-reading-together.png HTTP/1.1" 206 178198 "https://bookmate.life/main" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36"
```

tomcat에서는 오류 메세지가 출력 되지 않는 것을 보아 WebServer의 문제로 파악

### 문제의 일반적인 원인

읽기, 실행 권한이 부족하여 일어나는 현상으로 오류가 나는 폴더에 권한을 부여해 주어야 한다.

1. nginx 작업자를 ubuntu로 변경
    
    ```bash
    **user ubuntu;**
    ```
    
2. 권한 부여
    
    ```bash
    sudo chown -R ubuntu:ubuntu /var/lib/nginx/proxy/
    ```
    
3. nginx 재실행
    
    ```bash
    sudo systemctl reload nginx
    ```