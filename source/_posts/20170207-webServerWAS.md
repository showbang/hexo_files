---
title: webServer와 WAS의 차이점
categories:
  - etc
  - web
tags:
  - null
date: 2017-02-07 10:59:02
thumbnail: /typistShow/image/webServer.gif
---

#### WebServer와 WAS의 차이점
##### Web Server
Web browser client로부터 HTTP Request를 받아 자료콘텐츠에 따라 HTTP에 반응합니다.
Client가 GET,POST,UPDATE,DELETE등의 메소드를 이용하여 Request를 요청하면,
그에 해당하는 결과값을 돌려주는 기능을 합니다. Client가 요청한 것 중에 웹서버 자체적으로
처리할 수 없는 것들을 Tomcat과 같은 컨테이너나 PHP모듈과 같이 처리가 가능한 곳으로 넘겨,
처리결과를 받아 Client에게 전송해주는 역할도 수행합니다.
##### WAS(Web Application Server)
웹 기반 시스템 개발을 용이하게 해주며 안정적인 트랜젝션 처리를 해주는 미들웨어 시스템.
Client와 SErver간 Application 연동을 해줍니다. 웹서버에 Container가 추가된 것이,WAS.
Container는 JSP,SErvlet등의 구동 환경을 제공하여 동적 Data처리를 가능하게 만들어줍니다.

{%asset_img webServer.gif WebServer%}
{%asset_img WAS.gif WAS%}

위의 그림을 보면 볼 수 있듯이 WAS에서는 Application Server에서의 코드와 데이터를
조작할 수 있게 하여 동적인 데이터로 처리할 수 있게 만들어 주는 역할을 합니다.
우리가 흔히 쓰는 Apache가 대표적인 WebServer이며, Tomcat은 Apache사에서 제공하는
WAS입니다.

WAS가 WebServer를 포함하고 있으므로 WebServer가 필요하지 않다고 생각할 수도 있는데,
WebServer는 정적인 데이터를 처리하는 서버이기 때문에, 이미지나 단순 html 파일과 같은
리소스를 제공하는 서버는 WAS에서 제공하는 Container 기능이 필요가 없으며 WebServer를
이용하는 것이 더 빠르고 안정적입니다. 물론 DB에서 데이터를 주고 받거나, 프로그램상에서의
데이터 조작이 이루어져야 할때에는 WAS를 사용해야 합니다.

이러한 장단점들을 보완하기 위하여 두개의 서버를 연동하여 사용할 수 있습니다.
Client Request는 WebServer에서 받고 내부 프로그램은 WAS를 통하여 처리한다면,
정적,동적인 데이터를 모두 효과적인 처리를 할 수 있게 됩니다.

###### WebServer와 WAS를 연동하는 이유
- WAS는 WebServer만큼 정적인 데이터를 빠르며 안정적이게 처리하지 못한다.
- WAS는 WebServer만큼 다양한 옵션 및 환경 설정 기능을 제공하지 않는다.
- 상용화 되어있는 많은 사이트들이 Webserver기반으로 많은 시스템을 개발해놓은 상태.
- CGI,PHP등 ServerSide Application등과 다양한 모듈들을 WAS에서는 실행시킬수 없다.
