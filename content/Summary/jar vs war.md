---
tags:
  - etc
---
### JAR : Java Archieve

Class와 같은 Java 리소스와 속성 파일, 라이브러리 및 액세서리 파일이 포함되어있다.

JDK와 JRE만 가지고 실행이 가능하다.

### WAR : Web Application Archive

servlet / jsp 컨테이너에 배치 할 수 있는 웹 어플리케이션(Web Application) 압축 파일 포맷

JSP, SERVLET, JAR, CLASS, XML, HTML, JAVASCRIPT 등 웹 어플리케이션이 구동되기 위한 기타 자원을 한 군데에 모아 배포하는데 사용되는 파일

WAR는 웹 관련 자원만 포함하고 있으며, 웹 어플리케이션을 쉽게 배포하고 테스트 할 수 있다.

WAR은 WEB-INF 및 META-INF 디렉토리로 사전 정의 된 구조를 사용, WAR파일을 실행하기 위해서는 Tomcat, Weblogic, Websphere등의 웹 서버(Web) 또는 웹 컨테이너(WAS)가 필요

WAR또한  JAR옵션을 이용해 생성하는 JAR파일의 일종으로 웹 어플리케이션 전체를 패키징 하기 위한 JAR파일