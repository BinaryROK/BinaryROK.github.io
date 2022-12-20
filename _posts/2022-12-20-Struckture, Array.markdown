---
layout: post
title:  "Array"
date:   2022-12-20 09:00:01 +0900
categories: jekyll update
tag : C++
---
배열<br/>
배열이란 많은양의 변수를 선언할때 편리하다.<br/>
배열선언시 배열명과 크기를 지정하는것은 다음과같다.<br/>
{% highlight ruby %}
int Array[10]={1, 41, 12, 32, 32, 12 ,21 35, 42 13};
{% endhighlight %}
이때 자료형은 모든 자료형을 지원하고 크기는 양의 정수만 가능하다. 또한 크기n의 배열의 인덱스는 0~(n-1)까지다.<br/>
배열은 다음과같이 선언할수도있다.
{% highlight ruby %}
int arr1[10]={1. 32. 14. 532. 34};
int arr2[]= {1,2,3,4};
int arr3[5];
{% endhighlight %}
arr1은 5번째 인덱스까지는 주어진값이 들어가고 그 이후 10번인덱스까지는 0으로 초기화된다<br/>
arr2는 자동으로 크기가 4로 선언된다.<br/>
arr3은 크기는 5 인덱스값은 쓰레기값으로 선언된다.<br/><br/>
이후 배열 요소에 접근하려면 다음과같이 하면된다
{% highlight ruby %}
int arr[3];
arr[0] = 5;
arr[1] = 3;
arr[2] = 4;
arr[3] = 5;<- 런타임에러
{% endhighlight %}
배열의 동적할당<br/>
선언할때 배열의 크기를 설정하는것을 정적할당이라고 한다.<br/>
정적할당을 할 경우 메모리가 남거나 모자랄수 있는데 동적할당을하면 메모리를 효율적으로 사용할수있다.<br/>
다음은 동적할당으로 배열을 선언한 뒤 인덱스값을 입력받아 변수값을 초기화하는 코드이다.
{% highlight ruby %}
int main()
{
	int* p;
	printf("배열의 크기를 입력하시오\n");
	int arr_size;
	cin >> arr_size; // arr_size의 변수값을 입력받는다.
	p = new int[arr_size];

	while (1)
	{
		printf("인덱스값을 입력하시오");
		int n;
		scanf_s("%d", &n);
		if ((arr_size <= n) | (n < 0)) // n이 인덱스범위 밖일경우 고장남을방지
		{
			printf("인덱스값 오류");
			return 0;
		}
		printf("변수값을 입력하시오");
		scanf_s("%d", &p[n]);
		printf("%d번째 인덱스값은%d\n", n, p[n]);
	}
}





{% endhighlight %}


{% highlight ruby %}
{% endhighlight %}
{% highlight ruby %}
{% endhighlight %}
{% highlight ruby %}
{% endhighlight %}
