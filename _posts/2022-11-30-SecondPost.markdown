---
layout: post
title:  "두번째"
date:   2022-11-30 09:04:40 +0900
categories: jekyll update
---
두번째 기록이다.
어제 라즈베리파이에 라즈비안을 인스톨하는것을 해봤다.<br/>
라즈베리파이 4.0과 32Gb SD카드를 준비하여<br/>
라즈베리파이는 자체적인 OS가 내장되어있지 않아 따로 SD카드에 라즈비안 OS를 인스톨한 후 해당 SD카드를 라즈베리파이에 삽입하여 사용한다.<br/>
라즈베리파이에 라즈비안 인스톨 후 원래 사용하던 PC에서 키보드마우스, 모니터, 렌선을 연결하고 마지막으로 C타입 전원까지 연결하여 작동시켰다.<br/>
해서 라즈베리파이의 터미널로 파이썬파일을 만들어 안에 코드를 입력하고 실행하는것까지 해보았다.

{% highlight ruby %}
cat > file.py - 파이썬파일 만든 후 데이터적어넣기
cat file.py - 해당파일 데이터 출력
python file.py - 해당파일 코드 실행

{% endhighlight %}


깃허브 관련용어를 하나도 몰라가지고 다른걸봐도 이해가안가서 정리해보았다.<br/>
  로컬저장소 - 내pc저장소 / 원격저장소 - 서버혹은 네트워크저장소 보통 로컬저장소에서 작업한 후 원격저장소로 보낸다.<br/>
  git init - git 저장소를 초기화 / git clone github에있는 원격저장소를 로컬로 복제하는 명령어<br/>
  branch 는 잘 이해를 못했다. / commit - 소스코드의 업데이트를 확정하여 git저장소에 저장된다.<br/>
  push - commit내용을 원격저장소로 업로드하는것 / pull - 원격저장소의 내용을 로컬저장소로 반영하는것 <br/>
  SSH - 클라이언트와 서버간 원격통신을 위한 프로토콜, 깃허브와 클라이언트를 인증한 후부터 push pull이 된다.<br/>
  
깃허브 저장소간 데이터 공유
{% highlight ruby %}
git add --all / 
git commit -m "변경사항" / 




{% endhighlight %}

  
  






{% highlight ruby %}

{% endhighlight %}
