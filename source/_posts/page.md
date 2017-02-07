---
title: contains, substring, indexOf
date: 2017-01-10 14:00:54
categories:
  - java
tags:
thumbnail: /typistShow/image/java.png
---

contains - 문자나 문자열을 포함하는지 확인 후 true,false 반환
substring - 문자열의 인덱스값을 받은 후, 인덱스값에 알맞는 문자 또는 문자열을 반환
indexOf - 문자나 문자열을 받아 그에 맞는 인덱스 값을 반환

사용법을 예로 들면

# contains

{% codeblock lang:java %}
String movieTitle="나는 네가 지난 여름에 한 일을 알고 있다.";
System.out.println("contains의 반환값 =>"+movieTitle.contains("여름"));
System.out.println("contains의 반환값 =>"+movieTitle.contains("겨울"));
{% endcodeblock %}
이렇게 contains의 인자값이 포함되어 있으면 true 없으면 false를 반환한다.

# substring

만약 인자값을 하나의 인덱스만 준다면 그 인덱스부터 문자열을 반환한다.
{% codeblock lang:java %}
String movieTitle="나는 네가 지난 여름에 한 일을 알고 있다.";
System.out.println("6번째 인덱스의 문자=>"+movieTitle.substring(6));
{% endcodeblock %}

인자값을 두개를 준다면 첫번째 인자값은 시작되는 인덱스를 두번째 인덱스는 끝나는 인덱스를 의미한다. 주의할 점은 끝나는 인덱스를 포함하지 않고 그전 인덱스까지만 출력한다. 
만약 밑의 코딩처럼 입력한다면 출력문은 아래와 같다. 네가에서 끝난게 아니라 네가다음의 공백까지 출력된다.
{% codeblock lang:java %}
String movieTitle = "나는 네가 지난 여름에 한 일을 알고 있다."
System.out.println("0번째 인덱스부터 6번째 인덱스까지의 문자열=>"+movieTitle.substring(0,6));
{% endcodeblock %}

# indexOf

문자를 줬을때는 그 문자의 인덱스를 문자열을 줬을때는 문자열이 시작하는 부분의 인덱스를 반환한다.
{% codeblock lang:java %}
String movieTitle = "나는 네가 지난 여름에 한 일을 알고 있다."
System.out.println("지난이라는 문자열을 포함한 인덱스의 시작값=>"+movieTitle.indexOf("지난"));
{% endcodeblock %}

``` bash

```