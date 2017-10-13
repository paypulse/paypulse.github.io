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

---
`부동 소수점 형식(Floating Point Types)`

부동 소수점 형식은 정수 뿐 아니라 유리수를 포함하는 실수 영역의 데이터를 다룬다.
부동 소수점 형식에는  float , double 두가지 있다.

`float : Floating Point`
단일 정밀도 부동 소수점 형식(7개의 자릿수만 다룸), 4byte(32bit), -3.402823e38 ~ 3.402823e38
float 형식은 숫자 뒤에 f를 붙이면, float 형식으로 간주.

`double : Double Precision Floating Point Format`
복수 정밀도 부동 소수점 형식(15~16개의 자릿수를 다룸), 8byte(64bit), -1.79769313486232e308~1.79769313486232e308
숫자 뒤에 아무 것도 없으면, double 형식으로 간주.

`decimal `
decimal 역시 실수를 다루는 데이터 형식.
29자리 데이터를 표현할 수 있는 소수 형식, 16byte(128bit),
숫자 뒤에 m을 붙이면, deciaml 형식으로 간주

double이 float에 비해 메모리를 두 배로 사용하지만, 그 만큼 float에 비해 데이터 손실이 적기 때문이다.
decimal의 한계 마저도 넘어서는 데이터를 처리해야 한다면, 그때는 그 알고리즘을 담은 복합 데이터 형식을 직접 작성해야 한다. 회계 프로그램이나 계산기를 프로그래밍 할때 float, double 보다는 decimal이 더 적합하다.

{% highlight ruby %}

using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            float   a = 3.141592653589793238462643383279f;
            double  b = 3.141592653589793238462643383279;
            decimal c = 3.141592653589793238462643383279m;

            Console.WriteLine(a);
            Console.WriteLine(b);
            Console.WriteLine(c);
        }
    }
}

{% endhighlight %}

---
`문자 형식과 문자열 형식`

char 형식은 정수를 다루는 데이터 형식 출신이지만, 수가 아닌 '가','a'... 문자 데이터를 다룹니다.

`char`

char 형식 변수에 데이터를 담는 방법도 다른 전수 계열 형식과는 약간 다르고, ` '' `로 문자를 감싸줘야 합니다.

`string`

여러개의 문자 형식을 묶어 처리하는 방식, 정해진 크기나 담을 수 있는 데이터의 범위가 따로 정해져 있지 않습니다.
변수가 담은 텍스트의 양에 따라 크기가 변하기 때문이다.  ` "" ` 로 문자를 감싸줘야 합니다.

{% highlight ruby %}

using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            char a = '안';
            char b = '녕';

            Console.WriteLine(a);
            Console.WriteLine(b);

            string c = "안녕하세요";
            Console.WriteLine(c);


        }
    }
}

{% endhighlight %}

---
`논리 형식 :Boolean Types`

논리 형식이 다루는 데이터는 True, False 딱 두가지 입니다.
논리 형식, 1byte(8bit)

{% highlight ruby %}
using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            bool a = true;
            bool b = false;

            Console.WriteLine(a);
            Console.WriteLine(b);
        }
    }
}

{% endhighlight %}

---
`object 형식 `

object 형식은 어떤 물건(데이터)이든지 다룰 수 있는 데이터 형식이라 말할 수 있습니다.
object는 모든 데이터 형식의 조상이 된다. 따라서 컴파일러는 어떤 형식의 데이터라도 object에 담아 처리 할 수 있다.

{% highlight ruby %}

using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            object a = 123;
            object b = 3.141592653589793238462643383279m;
            object c = true;
            object d = "안녕하세요";

            Console.WriteLine(a);
            Console.WriteLine(b);
            Console.WriteLine(c);
            Console.WriteLine(d);
        }
    }
}

{% endhighlight %}

---
`박싱과 언박싱`

object 형식이 모든 데이터 형식을 담을 수 있는데,이러한 매커니즘을 박싱, 언박싱이라 한다.

object 형식은 참조 형식이기 때문에, 힙에 데이터를 할당 한다.
값 형식의 데이터를 힙에 할당 하기 위한 박싱 기능을 제공 한다.

{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/boxing.png" width="339" height="254"/>
{% endfor %}

a라는 변수는 힙에 할당 되어 있고, 20은 stack에 할당 되어, a가 20을 가리키고 있다.

[if]
object a = 20;
int b = (int) a;

b는 a가 참조하고 있는 메모리로 부터 값을 복사하는 중이고, 이때, 박싱 되어 있는 값을 꺼내 값 형식 변수에 저장하는
과정을 일컬어 언박싱이라고 한다. - 형변환을 하는것을 언박싱 한다고 하나 보다-

{% highlight ruby %}

using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            int a = 123;
            object b = (object)a; //int a에 담긴 값을 boxing후 heap에 저장
            int c = (int)b; //b에 담긴 값을 언박싱 후 stack에 저장

            double x = 3.1414213;
            object y = x; // object 형식에 저장할땐 형식 변환 연산자를 지정하지 않으면, 암시적으로 object 형으로 변환
            double z = (double)y; //y에 담긴 값을 다시 언박싱 후 stack에 저장

            Console.WriteLine(a);
            Console.WriteLine(b);
            Console.WriteLine(c);

            Console.WriteLine(x);
            Console.WriteLine(y);
            Console.WriteLine(z);


        }
    }
}

{% endhighlight %}
