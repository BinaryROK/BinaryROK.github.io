---
layout: post
title:  "Python"
date:   2022-12-20 09:00:01 +0900
categories: jekyll update
tag : Python3
---
파이썬 공부하다가 며칠지나니까 전부 까먹어서 정리해야겠다고 마음먹었다.<br/>
일단 VisualStudioCode를 사용할거고 파이썬 파일에 코드를 작성하고 실행을할것이다.<br/>
Test.py를 실행하기위해 python .\Test.py 명령어로 실행하면 된다.<br/>
input()명령어는 키보드로 입력을받는다.
{% highlight ruby %}
k=input()
print(k)
print(k+30)
{% endhighlight %}
위 코드를 실행한후 10을 입력하면 타입에러가 난다<br/>
그 이유는 input명령어는 기본적으로 문자열로 받기때문에 숫자연산이 되지않기때문<br/>
따라서 숫자를 입력받을거면 다음과같이 int(intput())명령어를 사용해야한다.
{% highlight ruby %}
k= int(input("숫자를 입력하시오:"))//input괄호안에는 입력안내문이들어간다.
print(k)
print(k+5)
{% endhighlight %}
위 코드를 실행하면 다음과같은 결과를얻는다.
{% highlight ruby %}
숫자를 입력하시오:5
5
10
{% endhighlight %}
sys.stdin.readline() <br/>
input()보다 빠르게 입력을 받을수 있다. 개행문자(\n)을 없애려면 rstrip.()이필요하다<br/>
{% highlight ruby %}
import sys
p=[]
n=5
while n:
    n -=1
    line = sys.stdin.readline()
    p.append(line)
print(p) 
{% endhighlight %}
p.append(line)에서 append는 리스트맨뒤에 원소(리스트도가능)을 추가하는명령어
{% highlight ruby %}
12
32
123
412
53424
['12\n', '32\n', '123\n', '412\n', '53424\n']
{% endhighlight %}
이때 rstrip()을 사용하면
{% highlight ruby %}
import sys
p=[]
n=5
while n:
    n -=1
    line = sys.stdin.readline().rstrip()
    p.append(line)
print(p)
{% endhighlight %}
{% highlight ruby %}
12
32
123
412
53424
['12', '32', '123', '412', '53424']
{% endhighlight %}
위와같이 개행문자를 없앨수있다.<br/>
다음은 split()으로 문자열을 들여쓰기 기준으로 잘라주어 리스트로 만들어준다.
{% highlight ruby %}
import sys
p=[]
n=5
while n:
    n -=1
    line = sys.stdin.readline().rstrip().split()
    p.append(line)
print(p)
print(p[0][0])
print(p[0][1])
{% endhighlight %}
위 코드에서 p는 리스트로 정의되었지만 리스트안에 리스트가 들어가게된다.
{% highlight ruby %}
1 2 3
4 5 6
7 8 9
0 1 2
3 4 5
[['1', '2', '3'], ['4', '5', '6'], ['7', '8', '9'], ['0', '1', '2'], ['3', '4', '5']]
1
2
{% endhighlight %}
map(func,list)는 리스트의 모든원소가 해당함수를 수행하게해준다.<br/>
대표적으로 여러개의 문자를 입력받을때 사용한다.<br/>
{% highlight ruby %}
A,B = map(int,sys.stdin.readline().split())
print(A+B) #3
A,B = map(int,input().split() #1 2
print(A+B) #3
{% endhighlight %}
위 처럼 여러개의 변수값을 입력받을때 사용할수있다.<br/>
map함수에는 리스트가 들어가야하므로 반드시 split()을 사용하여 입력값을 리스트로 만들어줘야한다.<br/><br/>

출력
출력은 print()로 간단하게 할수있다.
{% highlight ruby %}
print("hello world my name is binary")//1)
print("hello","world", "my", "name","is", "binary")//2)문자열 사이 콤마가있으면 띄어쓰기가된다.
print("hello","world", "my", "name","is", "binary",sep="")//3) 띄어쓰기가 맘에안들면 sep명령어를쓰면된다.
print("hello",end=" ")//기본 개행문자인 \n을 다른것으로 바꿀수있다.
print("world",end=" ")//4-1)
print("my",end=" ")//4-2)
print("name",end=" ")//4-3)
print("is",end=" ")//4-4)
print("binary",end=" ")//4-5
{% endhighlight %}
위 코드를 실행하면  
{% highlight ruby %}
hello world my name is binary //1)
hello world my name is binary //2)
helloworldmynameisbinary ///3)
hello world my name is binary //4)
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

 {% highlight ruby %}
 
 {% endhighlight %}

 {% highlight ruby %}
 
 {% endhighlight %}

 {% highlight ruby %}
 
 {% endhighlight %}
