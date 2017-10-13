---
layout: post
title:  "2. Integral Type"
date:   2017-10-11 10:59:21 +0700
categories: CSharp
---
`Data 종류`

C#은 기본 데이터 형식(기본 데이터 형식, 상수, 열거형)을 부품으로 삼아 구성되는 복합 데이터 형식(구조체, 클래스, 배열)을 지원 한다.

---
`값 형식과 참조 형식`

Value Types : 변수가 값을 담는 데이터 형식 , stack 메모리 영역.

Reference Types : 변수가 값 대신 값이 있는 위치(참조)를 담는 데이터 형식, Heap 메모리 영역

---
`Stack 과 값 형식 `

값 형식의 변수는 모두 stack 영역에 저장 되고 코드 블록 안에서 생성된 모든 값 형식의
변수들은 프로그램 실행이 중괄호 "}"를 만나면 메모리에서 제거 된다.

---
`Heap 과 참조 형식`

Heap 메모리 영역은 저장되어 있는 데이터를 스스로 제거하는 메커니즘을 갖고 있지는 않습니다.
대신 CLR의 가비지 컬렉터가 있기 때문에, 힙에서 더 이상 사용하지 않는 객체가 있으면 쓰레기로 간주하고 제거 한다.

[EX] : object (참조 형식)

{
  object a = 10;
  object b = 20;
}

10, 20은 힙에 저장 되고, a와 b는 값이 저장된 힙의 주소만 스택에 저장.

---
`기본 데이터 형식`

C#이 제공하는 Primitive Types에는 15가지가 존재 한다.
문자열 형식, 오브젝트 형식 만 참조 형식에 해당하며, 나머지는 모두 값 형식 이다.

---
`숫자 데이터 형식`

{% highlight ruby %}
byte  : 부호 없는 정수 , 1byte (8bit), 0~255
sbyte : signed byte 정수, 1byte (8bit), -128 ~ 127
short : 정수, 2byte (16bit), -32,768 ~ 32.767
ushort: unsigned short, 2byte (16bit), 0 ~ 65,535
int   : 정수, 4byte (32bit), -2,147,483,648 ~ 2,147,483,647
uint  : unsigned int, 4byte (32bit), 0 ~ 4,294,967,295
long  : 정수, 8byte (64bit),  -922,337,203,685,477,508 ~ 922,337,203,685,477,507
ulong : unsigned long , 8byte (64bit), 0 ~ 18,446,744,073,709,551,615
char  : 유니코드 문자, 2byte (16bit)
{% endhighlight %}



---
`[EX] : sbyte/byte, short/ushort, int/uint, long/ulong`

{% highlight ruby %}
using System;

namespace Blog1
{
    class MainApp
    {
        static void Main(string[] args)
        {
            sbyte a = -10;
            byte b = 40;
            Console.WriteLine("a ={0}, b={1}", a,b);

            short c = -30000;
            ushort d = 60000;
            Console.WriteLine("c={0}, d={1}",c,d);

            int e = -10000000;
            uint f = 300000000;
            Console.WriteLine("e={0}, f={1}",e,f);

            long g = -500000000000;
            ulong h = 2000000000000000000;
            Console.WriteLine("g={0}, h={1}",g,h);
            Console.WriteLine();

        }
    }
}
{% endhighlight %}

---
[result]
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/integralType.png" width="430" height="92"/>
{% endfor %}

---
`Data Overflow`

부호가 없는 정수 일 경우, overflow시 0값으로 각 정수형 자료형이 가질 수 있는 최소 값이 되지만 부호가 있는 경우,
가장 최소 값은 - 범위의 값이 나온다.

각 데이터 형식의 최대 값을 넘어가는 데이터를 저장 할때는 오버 플로우가 일어나고, 최저값보다 작은 데이터를 저장하면 언더 플로우가 일어 난다.

데이터를 다루는 코드를 작성 할때는 다루려는 데이터의 범위와 변수의 형식을 적절하게 맞춰 주는 것이 필요.

{% highlight ruby %}

using System;

/*Overflow example*/

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            uint a = uint.MaxValue;
            Console.WriteLine(a);

            a = a + 1;
            //uint 가 가질 수 있는 최저값으로 출력이 된다.
            Console.WriteLine(a);

            //uint.MaxValue 대신에 int.MaxValue를 사용해보자
            int b = int.MaxValue;
            Console.WriteLine(b);

            b = b + 1;
            Console.WriteLine(b);

        }
    }
}

{% endhighlight %}
