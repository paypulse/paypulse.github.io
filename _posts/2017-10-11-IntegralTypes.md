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

---
`데이터 형식 바꾸기`

변수를 다른 데이터 형식의 변수에 옮겨 담는 것을 형식 변환(Type Conversion)이라고 한다.
박싱, 언박싱도 값 형식과 참조 형식 간의 형식 변환이라 할 수 있다.

`크기가 서로 다른 정수 형식 사이의 변환`

[EX] : 1byte 크기의 sbyte 형식과 4byte 크기의 int 형식 사이의 형식 변환 예제

{% highlight ruby %}
using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            sbyte a = 127;
            Console.WriteLine(a);

            int b = (int)a;
            Console.WriteLine(b);

            int x = 128;
            Console.WriteLine(x);

            sbyte y = (sbyte)x;  //오버 플로우 발생
            Console.WriteLine(y);


        }
    }
}
{% endhighlight %}

sbyte는 2byte 인데 4byte짜리를 형변환시 오버 플로우가 발생 한다.
부호가 있는 경우 , 가장 최소 값은 - 범위의 값이 나온다.

---
`크기가 서로 다른 부동 소수점 형식 사이의 변환`

정수 형식 사이의 변환 처럼 오버플로우 현상은 일어 나지 않지만, 정밀성에 손상을 입는다.

{% highlight ruby %}
using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            float a = 69.6875f;
            Console.WriteLine("a :{0}",a);

            double b = (double)a;
            Console.WriteLine("b :{0}",b);

            Console.WriteLine("69.6875 == b:{0}",69.6875 == b);

            float x = 0.1f;
            Console.WriteLine("x :{0}", x);

            double y = (double)x;
            Console.WriteLine("y :{0}", y);

            Console.WriteLine("0.1 == y : {0}", 0.1 == y); //false가 출력이 된다.

        }
    }
}

{% endhighlight %}

---
`부호 있는 정수 형식과 부호 없는 정수 형식 사이의 변환`

{% highlight ruby %}
using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            int a = 500;
            Console.WriteLine(a);

            uint b = (uint)a;
            Console.WriteLine(b);

            int x = -30;
            Console.WriteLine(x);

            uint y = (uint)x; // 언더 플로우
            Console.WriteLine(y);

        }
    }
}

{% endhighlight%}

---
`부동 소수점 형식과 정수 형식 사이의 변환`

부동 소수점 형식의 변수를 정수 형식의 변환 하면 데이터에서 소수점 아래는 버리고 소수점 위 값만 남긴다.

{% highlight ruby %}
using System;

namespace Blog2
{
    class MainApp
    {
        static void Main(string[] args)
        {
            float a = 0.9f;
            int b = (int)a;
            Console.WriteLine(b);

            float c = 1.1f;
            int d = (int)c;
            Console.WriteLine(d);

        }
    }
}

{% endhighlight %}

---
`문자열을 숫자로, 숫자를 문자열로 변환`

"12345"는 문자열 이지만, 12345는 숫자. 우리가 그동안 알고 있었던,
암묵적인 형변환으로 시도 해봤자 compile 조차 안된다.

문자열을 숫자로 변환시 필요 메소드 : Parse(), Convert.ToInt32or64..()

숫자를 문자로 변화시 필요 메소드   : ToString()

{% highlight ruby %}
using System;

namespace stringtonumber
{
    class MainApp
    {
        static void Main(string[] args)
        {
            //정수형 to 문자
            int a = 123;
            string b = a.ToString();
            Console.WriteLine(b);

            //부동 소수점형 to 문자
            float c = 3.14f;
            string d = c.ToString();
            Console.WriteLine(d);

            //문자 to 정수형
            string e = "12345";
            int f = Convert.ToInt32(e);
            Console.WriteLine(f);

            //문자 to 소수형
            string g = "1.232";
            float h = float.Parse(g);
            Console.WriteLine(h);  
        }
    }
}

{% endhighlight %}

---

`상수와 열거 형식`

상수 [Constants], 열거 형식 [Enumerator] : 변수와 달리 안에 담긴 데이터를 절대 바꿀 수 없는 메모리 공간 이다.

상수와 열거 형식을 변수 대신 사용하면 컴파일러가 소스코드를 컴파일 할때 프로그래머의 실수를 잡아 알려주고, 프로그램의 버그도 줄여 준다.

상수 형식 : 프로그래머의 실수를 방지하기 위해 사용 한다.
열거 형식 : 같은 범주에 속하는 여러개의 상수를 선언 할때 유용 하다. 열거 형식의 각 요소에 어떤 값도 주지 않았지만 열거 형식은 정수 데이터를 갖고 있음을 알 수 있다.

상수 키워드  : const
열거형 키워드: enum

[상수형 code]

{% highlight ruby %}
using System;

namespace BlogPosting
{
    class MainApp
    {
        static void Main(string[] args)
        {
            //const example
            const int MAX_INT = 2147483647;
            const int MIN_INT = -2147483647;
            Console.WriteLine(MAX_INT);
            Console.WriteLine(MIN_INT);
        }
    }

}
{% endhighlight %}

[열거형 code]

{% highlight ruby %}
using System;

namespace BlogPosting
{
    class MainApp
    {
        enum DialogResult { YES, NO, CANCEL, CONFIRM, OK }
        static void Main(string[] args)
        {
            Console.WriteLine((int)DialogResult.YES);
            Console.WriteLine((int)DialogResult.NO);
            Console.WriteLine((int)DialogResult.CANCEL);
            Console.WriteLine((int)DialogResult.CONFIRM);
            Console.WriteLine((int)DialogResult.OK);

        }
    }
}

{% endhighlight %}

`열거 변수가 아니고 열거 형식!`

위의 예제에서 선언한 DialogResult는 변수가 아니고 새로운 형식이다.

[열거 형식을 기반으로 변수로 만들고, 이를 사용 하는 예제 프로그램]

열거 형식의 각 요소는 기본적으로 컴파일러 로부터 값을 자동으로 할당 받지만, 프로그래머가 값을 직접 대입 할 수도 있다.


{% highlight ruby %}

using System;

namespace BlogPosting
{
    class MainApp
    {
        enum DialogResult { HEAD=0, YES, NO, CANCEL, CONFIRM, OK , END}
        static void Main(string[] args)
        {
            DialogResult result = DialogResult.YES;

            if(result == DialogResult.YES)
            {
                Console.WriteLine("This is Yes");
            }
            else
            {
                Console.WriteLine("Re Search again");
            }


        }
    }
}

{% endhighlight %}

---
`Nullable 형식`

0이 아닌 비어 있는 변수, 즉, null 상태인 변수, 변수에게 할당된 메모리 공간을 비워 둘 수 있도록 Nullable 형식을 사용하면 된다. 참조 형식은 사용 할 수 없다.

[Nullable 형식은 두가지 속성]
1. HasValue : 해당 변수가 값을 갖고 있는지 또는 그렇지 않은지를 나타낸다.
              - HasValue 속성이 False값을 갖고 있다면, 그 변수는 비어 있다는 의미
2. Value    : 변수에 담겨 있는 값을 나타낸다.

Nullable 형식을 사용 할때는 HasValue 속성을 확인 하거나, null과 같은지를 비교하여 변수가 비어 있는지를 사전 검사 하는 것이 필요 하다.  

Nullable Type 선언 : int? 변수명 = null;

{% highlight ruby %}
using System;

namespace BlogPosting
{
    class MainApp
    {
        static void Main(string[] args)
        {
            int? a = null;

            Console.WriteLine(a.HasValue);
            Console.WriteLine(a!= null);

            //변수 a에 값을 대입 후
            a = 3;
            Console.WriteLine(a.HasValue);
            Console.WriteLine(a != null);
            Console.WriteLine(a.Value);

        }
    }
}
{% endhighlight %}

---
`Var 키워드`

var 키워드를 사용하여, int, string 같은 명시적 형식 대신 var를 사용하여 변수를 선언하면, 컴파일러가 자동으로 해당 변수의 형식을 지정해 준다.

※ var 키워드 사용법

변수를 선언 하려면 반드시 선언과 동시에 초기화를 해줘야 한다. 왜냐하면 컴파일러 입장에서 데이터를 보고 형식을 결정 할 수 있기 때문이다.

지역 변수로만 사용 할 수 있다. 왜냐하면 var 키워드로 필드를 선언 하면 컴파일러가 무슨 형식인지 파악 할 길이 없기 때문이다.

{% highlight ruby %}
using System;

namespace BlogPosting
{
  class MainApp
  {
      static void Main(string[] args)
      {
          var a = 20;
          Console.WriteLine("Type: {0}, Value: {1}", a.GetType(),a);

          var b = 3.1414213;
          Console.WriteLine("Type: {0}, Value: {1}", b.GetType(), b);

          var c = "Hello, World";
          Console.WriteLine("Type: {0}, Value: {1}", c.GetType(), c);

          var d = new int[] {10,20,30};
          Console.WriteLine("Type: {0}, Value: ", d.GetType());
          foreach (var e in d)
          {
              Console.WriteLine("{0}", e);
          }

          Console.WriteLine();

      }
  }
}

{% endhighlight %}

---
`공용 형식 시스템`

공용 형식 시스템 : 모두가 함께 사용하는 데이터 형식 체계<br>
공용 형식 시스템의 형식은 각 언어 에서 코드에 그대로 사용 할 수 있습니다.

<table>
  <tr>
    <th>클래스 이름</th>
    <th>C#  형식</th>
    <th>C++ 형식</th>
    <th>Visual Basic</th>
  </tr>
  <tr>
    <td>System.Byte</td>
    <td>byte</td>
    <td>unsigned char</td>
    <td>Byte</td>
  </tr>
  <tr>
    <td>System.SByte</td>
    <td>sbyte</td>
    <td>char</td>
    <td>SByte</td>
  </tr>
  <tr>
    <td>System.Int16</td>
    <td>short</td>
    <td>short</td>
    <td>Short</td>
  </tr>
  <tr>
    <td>System.Int32</td>
    <td>int</td>
    <td>int or long</td>
    <td>Integer</td>
  </tr>
  <tr>
    <td>System.Int64</td>
    <td>long</td>
    <td>int64 </td>
    <td>Long</td>
  </tr>
  <tr>
    <td>System.UInt16</td>
    <td>ushort</td>
    <td>unsigned short</td>
    <td>UShort</td>
  </tr>
  <tr>
    <td>System.UInt32</td>
    <td>uint</td>
    <td>unsigned int or unsigned long</td>
    <td>UInteger</td>
  </tr>
  <tr>
    <td>System.UInt64</td>
    <td>ulong</td>
    <td>unsigned int64 </td>
    <td>ULong</td>
  </tr>
  <tr>
    <td>System.Single</td>
    <td>float</td>
    <td>float</td>
    <td>Single</td>
  </tr>
  <tr>
    <td>System.Double</td>
    <td>double</td>
    <td>double</td>
    <td>Double</td>
  </tr>
  <tr>
    <td>System.Boolean</td>
    <td>bool</td>
    <td>bool</td>
    <td>Boolean</td>
  </tr>
  <tr>
    <td>System.Char</td>
    <td>char</td>
    <td>wchar_t</td>
    <td>Char</td>
  </tr>
  <tr>
    <td>System.Decimal</td>
    <td>decimal</td>
    <td>Decimal</td>
    <td>Decimal</td>
  </tr>
  <tr>
    <td>System.IntPtr</td>
    <td>없음</td>
    <td>없음</td>
    <td>없음</td>
  </tr>
  <tr>
    <td>System.UIntPtr</td>
    <td>없음</td>
    <td>없음</td>
    <td>없음</td>
  </tr>
  <tr>
    <td>System.Object</td>
    <td>object</td>
    <td>Object*</td>
    <td>Object</td>
  </tr>
  <tr>
    <td>System.String</td>
    <td>string</td>
    <td>String*</td>
    <td>String</td>
  </tr>
</table>

<b>공용 형식 시스템 예제</b>
{% highlight ruby %}
using System;

namespace BlogPosting
{
    class MainApp
    {
        static void Main(string[] args)
        {
            System.Int32 a = 123;
            int b = 456;

            Console.WriteLine("a type:{0}, value:{1}", a.GetType().ToString(),a);
            Console.WriteLine("b type:{0}, value:{1}", b.GetType().ToString(),b);

            System.String c = "abc";
            string d = "def";

            Console.WriteLine("c type:{0}, value:{1}", c.GetType().ToString(),c);
            Console.WriteLine("d type:{0}, value:{1}", d.GetType().ToString(),d);
        }
    }
}

{% endhighlight %}
