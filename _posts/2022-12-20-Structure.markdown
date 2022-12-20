---
layout: post
title:  "Struct,String"
date:   2022-12-20 09:00:01 +0900
categories: jekyll update
tag : C++
---
구조체<br/>
객체가 가지는 성질이 하나 이상일경우 변수가 여러개가 필요하다.<br/>
이러한 경우 구조체를 사용하면 정리도 잘되고 편리하다.<br/>
이때 구조체의 변수들은 구조체 내의 멤버변수가되며 구조체는 사용자가 새로 정의하는 자료형이 된다.<br/>
때문에 컴파일러에 미리 선언하여야 사용할수있다<br/>
기본적인 구조는 다음과 같다.<br/>
{% highlight ruby %}
struct status
{
	std::string name;//<string> 필요
	int age;
	int ht;
};

int main()
{
	status David;
	David.name = "David";
	David.age = 17;
	David.ht = 170;//-> 구조체 내 멤버를 하나씩 초기화

	status Lucy = { "Lucy", 22, 175 };
	std::cout << David.name << "의 나이는" << David.age << "키는" << David.ht << "\n";
	std::cout << Lucy.name << "의 나이는" << Lucy.age << "키는" << Lucy.ht << "\n";
  //std::cout 출력함수 <iostream>필요 
}
{% endhighlight %}
위 코드를 실행하면
{% highlight ruby %}
David의 나이는 17 키는 170
Lucy의 나이는 22 키는 175
{% endhighlight %}
C++에서는 문자열 입출력을 <string>을 통해 간편하게 할수있다.<br/>
{% highlight ruby %}
struct status
{
	std::string name;//std::string 은 문자열자료형 name을 위한것
	int age;
	int ht;
};

int main()
{
	status Binary;// 구조체 Binary 선언
	std::cout << "Enter your full name\n";
	std::getline(std::cin, Binary.name);//문자열 사이에 띄어쓰기까지 입력받는 std::getline 
	std::cout << "Enter your age\n";
	std::cin >> Binary.age;
	std::cout << "Enter your height\n";
	std::cin >> Binary.ht;//숫자만 입력받을때는 std::cin >>
	std::cout << "Your name is" << Binary.name << "\nyour age is " << Binary.age << "\nyour height is " << Binary.ht;
}
{% endhighlight %}
위 코드의 출력은 다음과 같다.
{% highlight ruby %}
Enter your full name
이진수
Enter your age
24
Enter your height
177
Your name is이진수
your age is 24
your height is 177
{% endhighlight %}



{% highlight ruby %}

{% endhighlight %}

{% highlight ruby %}

{% endhighlight %}

{% highlight ruby %}

{% endhighlight %}
 
