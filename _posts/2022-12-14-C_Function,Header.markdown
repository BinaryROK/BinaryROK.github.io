---
layout: post
title:  "C 함수, 헤더"
date:   2022-12-14 09:00:01 +0900
categories: jekyll update
tag : 업무
---
함수, 헤더파일에 대해 알아보자<br/>
함수가 뭔지는 알고있다. 하지만 학교에서배울때는 하나의 소스코드에 메인함수 필요한함수 전부 때려박는식으로 했었는데<br/>
함수가 한두가지일때는 괜찮겠지만 10개20개100개가 넘어가는경우 말이안되게 복잡해지고 내가 함수를 선언했는지도 모를수있기에 메인코드에는 메인함수만두는것이 좋다.<br/>
해서 따로만드는게 좋다. 그리고 헤더파일에 함수들이 선언되어있는데 이 함수들을 호출해서 쓰기위해 가져오게되어있다.<br/>
기본적인 헤더파일로 <stdit.h> 혹은 <iosteam>등이 있고 내가 헤더파일을 새로 만들어서 가져올경우에는 "function_name"처럼 따옴표로 가져와야한다.<br/>
내가 메인소스코드로 Title.cpp를 가지고있고 함수를 선언 및 구현을 해서 가져오고싶다면<br/>
새 헤더파일Function.h에 선언하고 새 파일 Function.cpp에 구현을 해주면된다. 
{% highlight ruby %}
Function.h
int Function_name(int var1,int var2);//헤더파일에 함수 정의

Function.cpp
int Function_name(int var1,int var2)
{
  대충 함수내용;
  retrun = x;
}                   //함수 구현

Title.cpp
#include "Function.h"
#include <stdio.h>
int main()
{
  int var1;
  int var2;
  Function_name(var1, var2);//함수호출하기



  return 0;
}



{% endhighlight %}





{% highlight ruby %}
{% endhighlight %}
{% highlight ruby %}
{% endhighlight %}
{% highlight ruby %}
{% endhighlight %}
{% highlight ruby %}
{% endhighlight %}
{% highlight ruby %}
{% endhighlight %}
{% highlight ruby %}
{% endhighlight %}
{% highlight ruby %}
{% endhighlight %}
