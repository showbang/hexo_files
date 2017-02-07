---
title: 창 resize 방법
categories:
  - javascript
tags:
  - null
date: 2017-01-25 18:04:03
thumbnail: /typistShow/image/javascript.jpg
---


동적인 css로 코딩을 하지 않았을 경우 처음 창크기에 맞게 css가 조절된 후 css가 변경되지 않을 때가 있다.
이때는 jQuery를 이용해서 쉽게 resize를 시킬 수 있다.


```Java
$(window).resize(function(){
	//제어해야 할 코드
}).resize();

```