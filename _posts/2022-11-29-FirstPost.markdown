---
layout: post
title:  "첫번째"
date:   2022-11-29 09:04:40 +0900
categories: jekyll update
---
어제 블로그를 만들고 오늘 처음으로 글을쓴다. 이 글이 제대로 게시될지도 모르겠다.
1학년때 C++몇번 만져본거 제외하고는 아무것도 모르기에 앞으로 배울 파이썬 리눅스 등등 사실 들어보기만하고 아무것도 모른다.
어제 잠깐 파이썬 문법몇개 끄적여봤는데 지금 문제점이 사실 노베이스로 헤딩하는거라 기본적인 용어를 모른다. 그래서 관련자료를봐도 이해를못하는게 대부분이다.
어제 처음으로 디렉토리의미를 찾아봐서 알게됐고 앞으로 배우는것들을 정리해서 포스트로 올려야겠다.
잘 할수있을지는 모르겠는데 열심히 해봐야지 
  깃허브 블로그 변경사항 업로드 하는법
  git cmd에서 디렉토리를 C:\Users\Administrator\BinaryROK.github.io 로 가서
  {% highlight ruby %}
  git add --all  
  git commit -m "내용"
  git push -u origin main
{% endhighlight %}
그냥 하라는대로 해서 각 명령이 어떤의미를 가지는지는 모른다 공부해봐야겠다.

터미널 - 프로그래밍명령어를 입력하는 소프트웨어
GUI - Graphical User Intetface 시각적으로 보기 편한 인터페이스
CLI - Command Line Interface 신속하고 편리하기에 CLI에 익숙해져야한다
WLS - Window Subsystem for Linux 윈도우에서 리눅스환경으로 CLI사용하기위한 것
pwd - print workign directory 현재 디렉토리 위치
cd - change directory 디렉토리 위치변경 (cd 경로 / cd .. / cd bin)
ls - list directory contents

디렉토리, 파일명 입력할때 한두문자 입력하고 탭누르면 자동완성됨

파일, 디렉토리 생성 삭제
{% highlight ruby %}
mkdir 디렉토리이름 -디렉토리생성  / mkdir -p 디렉토리이름1/디렉토리이름2 - 하위디렉토리까지생성
rmdir 디렉토리이름 -디렉토리삭제 디렉토리가 비어있어야 삭제가능 / rm -r 디렉토리 - 파일을가지고있는 디렉토리삭제
touch 파일명 - 깡통파일생성 혹은 최종수정시간 변경
cat > 파일명 - 생성한 파일에 데이터입력가능 혹은 생성된파일 데이터 다시입력 ctrl+c로 종료 / cat 파일명 - 파일 데이터 출력
mv 기존파일명 변경파일명 - 파일명 변경하기  / rm 파일명 디렉토리명(..시 상위디렉토리) - 파일을 디렉토리로 이동 / rm 파일명 -파일 삭제 
{% endhighlight %}


{% highlight ruby %}

{% endhighlight %}
