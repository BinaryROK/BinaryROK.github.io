---
layout: post
title:  "세번째"
date:   2022-12-01 09:48:00 +0900
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
이런경우에는 라즈베리파이 configuration에서 VNC enable로 설정하면 해결된다. 이때 라즈베리파이에 인터넷연결이 안되어있으면 VNC연결이 안된다. 이것때문에 많이 실패했었다.<br/>
원래는 라즈베리파이4에 와이파이모듈이 내장되어있는데 내가 설정을 잘못건들여서 지금 와이파이가 안된다. 정 안되면 포멧을해야할것같다.<br/>

설정을 바꿔서 와이파이가 된다. wpa_supplicant 파일을 수정해서 와이파이 설정을 했다. 이때 SSID가 뭔지몰랐는데 그냥 와이파이 이름이었다.<br/>
와이파이설정을 하고 vnc가동을 하니 이제 데스크탑에서 라즈베리파이로 원격조작이 가능해졌다. 힘들게 모니터 키보드마우스를 옮길필요가 없어졌다.<br/><br/>

라즈베리파이에서 VNC설정하는법
{% highlight ruby %}
터미널에 vncserver -geometry 1280x1024    / ctrl alt t 누르면 터미널이나온다. vnc서버여는명령


{% endhighlight %}
하지만 라즈베리파이 재부팅 후에는 다시 vnc서버를 열어줘야한다 그래서 좀 불편하다. 해결방법을 찾아봐야지<br/><br/>
vnc서버는 재부팅해도 자동으로 열린다. 다만 재부팅후 열리는데 시간이 좀 걸리니까 기다려주면된다.







{% highlight ruby %}



{% endhighlight %}
