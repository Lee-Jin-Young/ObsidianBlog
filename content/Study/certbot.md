---
tags:
  - Linux
---
Nginx 설치 / 설정

1. 서버의 패키지 목록 업데이트
    
    `sudo apt update`
    
    `sudo apt upgrade`
    
    `sudo apt autoremove`
    
2. *Nginx 설치
    
    `sudo apt install nginx`
    
3. Nginx 실행
    
    `sudo service start nginx`
    
    **start: unrecognized service 오류 ⇒ active(running) 상태임을 확인하였다.
    
4. Nginx 설정
    
    Version 확인 : `sudo dpkg -l nginx` ⇒ 1.18.0-6ubuntu14.4
    
    경로 확인 : `sudo find / -name nginx.conf` ⇒ /etc/nginx/nginx.conf
    
    해당 폴더로 이동 : `cd /etc/nginx`
    
    설정 파일 수정 위한 편집기 실행 : `sudo vim nginx.conf`
    
    구동 테스트 : `netstat -lntp` 80번 포트가 리스닝 상태이면 실행 된 상태
    
5. 내장 톰캣으로 포트 리다이렉트
6. 도메인 연결
7. certbot  설치
    
    `sudo apt-add-repository ppa:certbot/certbot`
    
    `sudo apt install certbot`
    
    `sudo apt-get install python-certbot-nginx`
    ⇒ ***Unable to locate package python-certbot-nginx
    
8. 도메인 인증을 통해 인증서 발급
    
    `sudo certbot --nginx -d dns`
    

참고 자료

---

*[https://t-okk.tistory.com/154](https://t-okk.tistory.com/154)

**[https://sarc.io/index.php/nginx/2274-ubuntu-nginx](https://sarc.io/index.php/nginx/2274-ubuntu-nginx)

***[https://qteveryday.tistory.com/318](https://qteveryday.tistory.com/318)