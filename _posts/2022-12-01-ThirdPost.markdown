---
layout: post
title:  "Welcome to Jekyll!"
date:   2022-12-01 08:48:00 +0900
categories: jekyll update
---
3번째 출근
어제는 라즈베리파이를 AP모드로 설정하여 VNC로 데스크탑과 원격으로 연결을 해보았다. AP모드는 AccessPoint로 쉽게말해 라즈베리파이를 공유기처럼 사용하는것이다.<br/>
먼저 라즈베리파이에서 터미널을 열어 다음 두 패키지를 인스톨해야한다.<br/>

{% highlight ruby %}
sudo apt-get install hostapd
sudo apt-get install dnsmasq
{% endhighlight %}

위 두개의 패키지를 이용하여 AP 설정을 한 후 데스크탑에서 해당 wifi에 연결을 한다.<br/>
후에 데스크탑에서 VNC viewer에 라즈베리파이의 ip를 입력하여 연결하면 된다. 여기서 The connection was refused by the computer라고 뜰수도있는데.<br/>
이런경우에는 라즈베리파이 configuration에서 VNC enable로 설정하면 해결된다.






{% highlight ruby %}



{% endhighlight %}
