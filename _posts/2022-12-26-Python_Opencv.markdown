---
layout: post
title:  "Python_Opencv"
date:   2022-12-26 09:00:01 +0900
categories: jekyll update
tag : Python3
---
  파이썬에서 opencv를 통해 이미지,영상을 출력할수가 있다.
  간단한 이미지 출력 예시
 {% highlight ruby %}
  import cv2
  image = cv2.imread("D:\Clang\Python\image\ABC.jpg")//경로에있는 이미지 변수에저장
  cv2.imshow('Test',image)
  cv2.waitKey()
 {% endhighlight %}
 opencv를통해 내장되어있는 카메라를 사용할수도 있다.
 {% highlight ruby %}
  import cv2

  capture = cv2.VideoCapture(0)
  #VideoCapture(index)는 내장 혹은 외장카메라 인덱스를기입한다. 기본내장카메라는0번<br/>
  후에 연결하는 외장카메라는1~n인덱스가된다.
  capture.set(cv2.CAP_PROP_FRAME_WIDTH,640)
  capture.set(cv2.CAP_PROP_FRAME_HEIGHT,640)
  #capture.set(propid,value)는 카메라의 속성과 그 속성의 값을  설정한다.<br/>
  예제에서는 너비와 높이를 설정하였다.
  while cv2.waitKey(33) < 0:
      ret, frame = capture.read()
      cv2.imshow("VideoFrame",frame)

  capture.release()
  cv2.destroyAllWindows()
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
