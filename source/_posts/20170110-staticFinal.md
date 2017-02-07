---
title: static, final, abstract
categories:
  - java
tags:
  - null
date: 2017-01-10 16:37:03
thumbnail: /typistShow/image/java.png
---

### Related Posts

# static
 -field와 method 앞에 붙는다.
 -method 앞에 붙을경우는 field를 변경하지 못한다.
 -static은 class를 같이 가지고 메모리에 적재되기 때문에 생성자 없이 ClassName으로 접근 가능하다.

 # final
 -마지막 상태값을 가져야 할때 쓰는 keword.
 -변수에 final이 붙으면 변수를 상수화 시킨다.
 -final이 Class에 붙으면 그 Class는 더이상 확장시키지 않는다.
 -final이 method에 붙으면 그 method는 더이상 overriding 하지 않는다.
 -final이 field에 붙으면 그 값은 더이상 상태값을 변경시키지 않는다.

 # abstract
 -오버라이딩하여 하위클래스에서 메소드를 호출하게 되면 상위클래스에 있는 메소드는 사용되지 않기 때문에 상위클래스의 메소드는 abstract를 이용하여 추상화시킨다.