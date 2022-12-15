---
layout: post
title:  "C 포인터, 비트연산자"
date:   2022-12-14 09:00:01 +0900
categories: jekyll update
tag : 업무
---
최근에는 백준 문제풀이를 통해 파이썬을 공부중이고 c++은 문법을 공부하고있다.<br/>
C++에서 이제 간단한 반복문, 조건문은 사용할수 있게되었고 비트연산자, 포인터, 헤더파일에 대해서도 조금 배웠다.<br/><br/>
반복문
반복문은 for while이 있으며 for문의 기본형식은 다음과같다.
{% highlight ruby %}
for (int i=0; i<10; i++)
{
  printf("%d", i);
}
를 실행하면 123456789 가 출력이된다.

{% endhighlight %}
while문은 해당 조건이 충족된다면 반복되는데 이를통해 무한루프를 만들수도있다.
{% highlight ruby %}
int i=0;
while (i <10)
{
  i++;
  printf("%d",i);
}
를 실행하면 출력은 12345678910이된다. 이를 다음과같이활용하면 무한루프가된다.
while(1)
{
  printf("O");
}
while(1)에서 1은 true를 나타내므로 항상 참이어서 무한루프가된다.

{% endhighlight %}

if 조건문은 조건이 충족되면 실행하고 충족하지않으면 그냥 넘어간다.
{% highlight ruby %}
	int i = 5;
	if (i < 5)
	{
		printf("low");
	}
	else if (5 < i)
	{
		printf("high");
	}
	else
	{
		printf("same");
	}
  만약 i가 5보다 작다면 low, 크다면 high, 같다면 same이 출력된다.
{% endhighlight %}

<br/>비트연산자<br/>
비트연산자는 이해할때 좀 힘들었다. 우선적으로 16진법표기, 비트, 바이트에대해 이해할필요가 있었다.<br/>
16진법은 0xXXXXXXXX로 표기하는데 만약 0x04라면 0x00000004에서 06개를 생략한것이다.<br/>
이때 16진법은 0~F로 숫자로치면 0~15까지 표기가 가능하다. 이는 딱16개로 2진수로 표현을한다면 XXXX로 표현이 가능하다.<br/>
예를들어 0x0F의 경우 0000 1111 이 되는것이다. 0x00000000은 0000 0000 0000 0000 0000 0000 0000 0000로 총32비트(4바이트)표현이 되는것이다.<br/>
기본적으로 MSB(MostSignificantBit)는 최상위비트 LSB(LeastSignificantBit)는 최하위비트를 의미한다.<br/>
이제 비트연산자에 대해 알아보자 <br/>
비트연산자는 &(and) |(or) ^(Xor) ~(not) <<(left shift) >>(right shift) 로 총 6가지가있으며<br/>
&는 모두1일때만 1 , or은 하나라도 1이면 1, not은 반전, Xor은 서로다른비트면1(01 or 10)으로 연산이 되며
Shift란 비트를 지정한만큼 이동시키는것이다. <<은 x2를 >>는 /2를 의미하며 각각 적혀있는방향으로 한칸 움직이게된다.<br/>
예를들어 1 << 4라면 0000 0001에서 0001 0000이 되는것이다. / 8 >>1 은 0000 1000을 0000 0100이된다.<br/>

이를 응용하여 GetBit, PrintBit, SetBit, ResetBit등의 함수를 만들수있다.<br/>
먼저 PrintBit(num)는 숫자num의 비트를 출력하는 함수이다.
{% highlight ruby %}
void PrintBit(int Num) //내가짠거
{
	int i ;
	int j = 1;
	int vv = 1;
	for (i = 31; i >= 0; i--, j++) //출력을 MSB부터해야하므로 31번비트부터 출력한다.(비트는0번으로시작해 31번까지있다.)
	{
		vv =1 << i;   // 맨처음i=31일때 vv는 0x80000000이되고 다음i=30은 vv=40000000이된다.
		if ((vv & Num) != 0)
    //위 조건은 vv&Num의 결과가 0이 아닐때 충족된다.<br/>and연산은 모두 1이어야 1이되므로 vv는 31번비트만 1이고 나머지는 0이기에 연산결과 0~30비트는 0이고정으로되고 <br/>
    만약 Num의 31번비트가 1이라면 결과는 0이아니기에 위 조건이 충족되고 0이라면 결과가 0이기에 충족이되지않는다.<br/>
    이때 결과 0이란 0x00으로 0000 0000 0000 0000 0000 0000 0000 0000을 의미한다.
		{
			printf("1");
		}
		else
		{
			printf("0");
		}
		if (j % 4 == 0)// 이 코드는 비트를 4개마다 끊어준다.
		{
			printf(" ");
		}
	}
	printf("\n");
}
{% endhighlight %}
<br/>
GetBit(k,n)은 숫자k의 n번째 비트를 출력하는 함수다. 이때 n은 0~31이다. LSB가0번째 MSB가31번째를 의미한다.<br/>
{% highlight ruby %}
void GetBit(int K, int n)
{
	int tem = 1 << n;
	if ((K & tem) != 0)//위 PrintBit와 동일한 알고리즘이다.
	{
		printf("0x%x 의%d번째비트는 1입니다.", K, n);

	}
	else
	{
		printf("0x%x 의%d번째비트는 0입니다.", K, n);
	}

}
{% endhighlight %}
<br/>
SetBit(int* num,int n)은 포인터의 개념을 먼저 알아야 이해할수있다.<br/>
포인터. 포인터는 무엇이고 왜 쓰고 왜 중요한가.<br/>
포인터는 어떤 변수가 저장된 메모리의 '주소'를 값으로하는 변수이다.<br/>
다음 예시를 보자
{% highlight ruby %}
	int a = 4;
	printf("a=%d\n", a);//a=4
	int* ptr = &a;//prt변수값으로 a의 주소가 들어간다.
	printf("%x %x\n", ptr, &a);//ptr과 a메모리주소값이 동일하다.
	printf("a=%d\n", a);//a=4
	*ptr = 10;//*ptr하면 a의주소의 값을 같이 변경시킨다.
	printf("a=%d", a);//a=10, a값을 변화시키지않았는데 a의주소에가서 값으변경하니 a값이 변했다.
{% endhighlight %}
포인터를 배울때 왜 굳이 주소를 찾아가 값을바꾸는지 궁금했다. 그냥 변수값을 변경하면 되는것이아닌가? 했는데 이에는 몇가지 이유가있다.<br/>
첫번째 이유는 그냥 변수값을 변경했을때 변경이 안되는경우이다. 이게 무슨말이냐면 함수를 호출할때 생기는 일이다.
다음 함수들을 보자
{% highlight ruby %}
void test(int i);
void test(int i)
{
	i = 0;
	printf("i=%d\n", i);
	i += 5;
	printf("i=%d\n", i);
}
void testptr(int *ptr);
void testptr(int *ptr)
{
	printf("*ptr=%d\n", *ptr);
	*ptr += 10;
	printf("*ptr=%d\n", *ptr);
}

int main()
{
	int i = 0;
	printf("i=%d\n", i);
	test(i);
	printf("i=%d\n", i);
	int j = 10;
	printf("j=%d\n", j);
	testptr(&j);//*ptr=&j
	printf("j=%d\n", j);
}
{% endhighlight %}
위 코드를 실행해본다면 출력은 다음과같이 나온다.<br/>
{% highlight ruby %}
i=0
i=0
i=5
i=0
j=10
*ptr=10
*ptr=20
j=20
{% endhighlight %}
이게 무슨의냐면 첫번째함수 test를 호출하였을때 i+=5가 반영되어 출력되었지만 함수호출이 끝난 후에 다시 i를출력하니 i=0이출력된다.<br/>
이는 위 변동사항이 생긴것이아닌 void test의 i와 main함수의 i가 다른 변수임을 보여준다. 따라서 main에 정이된i는 변동사항이 없는것이다.<br/>
하지만 나는 main함수의 변수를 다른함수를 호출하여 변경하고싶은거다. 그러기위해서는 testpt을 보자<br/>
testptr함수는 호출이 끝난 후 main함수의 변수 j가 변경되었음을 알수있다. 이는 호출된함수 testptr이 main함수의 변수 j의 주소에 들어가 값을 변경해주고 왔기때문이다.<br/>
두 함수는 겉보기에는 비슷해보이지만 작동하는방식이 완전 다르다. 이러한 경우를 위해서 포인터는 꼭 사용할줄 알아야한다.<br/><br/>

포인터를 사용할때의 두번째 이점은 메모리할당을 줄일수 있다는것이다. <br/>
위 두개의 함수를 다시보자. 
{% highlight ruby %}
void test(int i);
void test(int i)
{
	i = 0;
	printf("i=%d\n", i);
	printf("add_i=%x\n", &i);//주소
	i += 5;
	printf("i=%d\n", i);
}
void testptr(int *ptr);
void testptr(int *ptr)
{
	printf("*ptr=%d\n", *ptr);
	*ptr += 10;
	printf("*ptr=%d\n", *ptr);
	printf("ptr=0x%x\n", ptr);//주소
}

int main()
{
	int i = 0;
	printf("i=%d\n", i);
	test(i);
	printf("i=%d\n", i);
	printf("add_i=0x%x\n", &i);//주소
	int j = 10;
	printf("j=%d\n", j);
	testptr(&j);//*ptr=&j
	printf("j=%d\n", j);
	printf("add_j=0x%x\n", &j);//주소
}
{% endhighlight %}
각 함수및 메인함수에 변수 i j ptr의 주소를 출력을 넣었다 위 코드를 실행하면
{% highlight ruby %}
i=0
i=0
add_i=dbf6a4
i=5
i=0
add_i=0xdbf784
j=10
*ptr=10
*ptr=20
ptr=0xdbf778
j=20
add_j=0xdbf778
{% endhighlight %}
가 나오게된다. 여기서 변수i의 경우 test함수의 i와 main의i는 같은이름이지만 주소가 다르다. 이는 둘이 다른 변수임을 의미한다.<br/>
하지만 ptr의 값과 j의 주소값이 같다. 이는 ptr=&j라는 의미이며 둘은 이름은다르지만 같은것이라는것을 보여준다.<br/>
여기서 포인터사용의 이점을 볼수있다. 포인터를사용한 testptr함수의 경우 기존main함수에 할당된 메모리만 사용하는데<br/>
test함수는 함수내의 변수i에게 메모리를 새로 할당해준다 이는 메모리사용량을 늘리며 위 예시에서는 별 차이가 없지만<br/>
만약 포인터로 지정한 변수에게 할당된 메모리가 높다면 그거와 같은양의 메모리를 할당해줘야하므로 메모리낭비가 심해진다<br/>
따라서 이러한경우 포인터를 사용해준다면 메모리사용량을 아낄수있게된다.<br/><br/>
이제 포인터에대해 알게되었으니 SetBit(int *num,int n)에대해 알아보자<br/>
이는 변수num의 n번비트를 1로 고정해주는 함수이다.(비트는0번부터31번까지이니 햇갈리지말자)
{% highlight ruby %}
void SetBit(int* num, int n) 
{
	int vv = 1 << n; //1번비트를 1로 고정하겠다.
	*num |= vv;// *num= num|vv 과 동일하다.
	//PrintBit(*num); // for debugging
}
int main()
{
	int num = 0xFFF0;
	int n = 1;
	
	PrintBit(num);//위에있는 PrintBit함수를 호출한것이다.
	printf("SetBitPTR\n");
	SetBit(&num, n);
	PrintBit(num);
}
{% endhighlight %}
위 코드의 출력은 다음과같다.
{% highlight ruby %}
0000 0000 0000 0000 1111 1111 1111 0000 // 1번비트값은 0
SetBitPTR
0000 0000 0000 0000 1111 1111 1111 0010 // 1번비트값이 1이되었다.
{% endhighlight %}
위 함수에서 핵심이되는 알고리즘은 *num|=vv 라고할수있다.<br/>
이는 *num= num|vv이며 위 예시로 n=1이므로 vv=0x02로 1번비트를제외하고 전부 0이다.<br/>
따라서 vv와 *num의 or연산을하게되면 1번비트를 제외하고는 *num의 비트값을그대로 가져가고 num의 1번비트는 0이든1이든 1이된다.</br>
따라서 *num의1번비트가 Set되었다고 볼수있다.<br/><br/>

마지막으로 ReSetBit에해 알아보자<br/>
ReSetBit(int *num, n)은 *num의 n번비트를 0으로설정하는 함수다. 다음 함수를 보자
{% highlight ruby %}
void ReSetBit(int* num, int n)
{
	int vv = 1 << n;
	*num ^= vv;		
	if ((*num&vv)!= 0)//*num의 n번비트가 1이라는뜻
	{
		*num ^= vv;
	}
	PrintBit(*num);	
}					
int main()
{
	int num1 = 0xFFF0;
	int num2 = 0xFFFF;
	PrintBit(num1);
	PrintBit(num2);
	int n = 1;
	ReSetBit(&num1, n);
	ReSetBit(&num2, n);
}
{% endhighlight %}
위 코드의 출력은 다음과같다.
{% highlight ruby %}
0000 0000 0000 0000 1111 1111 1111 0000//num1
0000 0000 0000 0000 1111 1111 1111 1111//num2
0000 0000 0000 0000 1111 1111 1111 0000//ReSet num1 0->0
0000 0000 0000 0000 1111 1111 1111 1101//ReSet num2 1->0
{% endhighlight %}
num1의 1번비트 0, num2의 1번비트1 모두 0으로 출력된다.<br/>
ReSetBit알고리즘은 SetBit보다 조금더 복잡한데 주요알고리즘은 다음내용이다<br/>
{% highlight ruby %}
	int vv = 1 << n;
	*num ^= vv;		//1번
	if ((*num&vv)!= 0)//*num의 n번비트가 1이라는뜻//2번
	{
		*num ^= vv;
	}

{% endhighlight %}
위 코드의 1번문장을 보면 주어진 변수의값 *num과 n번비트만 1인 vv를 xor연산을한다.<br/>
이경우 n번비트를 제외한 모든 비트는 *num을따라가고 n번비트는 반전이된다.<br/>
이후 2번 조건문의내용은 *num의 n번비트가 1이면 조건을 만족한다.<br/>
조건문 안에서의 *num ^= vv;는 1번식과 마찬가지로 n번비트는 반전 n번제외비트는 *num을 따라간다.<br/>
따라서 n번비트가 원래 0인경우 n번비트를 두번 반전하여 그대로 0이되게하고 n번비트가1인경우 반전을 한번만하여 0이되게한다.
<br/><br/>다른 알고리즘으로 ReSetBit함수를 구현할수있다.
{% highlight ruby %}
void ReSetBit(int* num, int n)
{
	int vv = (1 << n); vv ^= 0xFFFFFFF; *num &= vv;
	//*num &= ((1 << n) ^0xFFFFFFFF); //윗줄을 한줄로 줄인것이다.
	PrintBit(*num);
}
{% endhighlight %}
두 함수의 차이는 조건문의 유무인데 조건문이 있는경우 연산속도가 느려져 위처럼 구현하는것이 더 유리하다.<br/>
한두번호출할때는 차이가 없지만 호출횟수가 많아질수록 격차가 벌어질것이다.







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
