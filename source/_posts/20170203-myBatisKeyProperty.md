---
title: myBatis에서 insert 후 원하는 컬럼 select 해오기
categories:
  - etc
  - myBatis
tags:
  - null
date: 2017-02-03 09:49:08
thumbnail: /typistShow/image/myBatis.png
---

#### myBatis에서 insert 후 원하는 컬럼 select 해오기
코딩을 하면서 insert후에 insert한 컬럼의 값을 가져올 일이 있습니다.
이때 keyProperty를 이용하면 insert 후 return값으로 int값이 아닌
원하는 컬럼의 값을 return받을 수 있습니다.

``` xml
<insert id="insertBaby" parameterType="baby" 
		useGeneratedKeys="true" keyProperty="bNo">
	INSERT INTO baby (
		 B_NAME
		 ,B_BIRTH
		 ,B_SEX
		 ,B_NATURE
		 ,B_TYPE
		 ,B_PHOTO
		 ,U_NO
	) VALUES (
	 #{bName} 
		 ,#{bBirth:VARCHAR} 
		 ,#{bSex}
		 ,#{bNature:VARCHAR}
		 ,#{bType:VARCHAR}
		 ,#{bPhoto:VARCHAR}
		 ,#{mom.uNo}
	)	
</insert>
```
위 코드처럼 userGeneratedKeys의 값을 true로 지정해주고,
keyProperty값에 return받을 column을 지정해줍니다. 
이렇게 되면 insert 후 myBatis에서 return해주는 값은
insert한 bNo값을 return해줍니다. keyProperty를 이용하면
insert 후 select해오는 로직을 생략할 수 있습니다.