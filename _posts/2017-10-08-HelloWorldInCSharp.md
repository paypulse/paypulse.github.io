---
layout: post
title:  "1.Hello, World!"
date:   2017-10-08 10:59:21 +0700
categories: Language
---
`Hello, World`

I used a visual studio 2012 version IDE.
{% highlight ruby %}
using System;

namespace HelloWorld
{
    class HelloWorld
    {
        //Program start.
        static void Main(string[] args)
        {
            Console.WriteLine("HelloWorld");
        }
    }
}
{% endhighlight %}

---
[result]
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/HelloWorld.png" width="460" height="175"/>  
{% endfor %}

---
`Check out the exe file to run a windows explore.`
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/helloworldExe.png" width="779" height="208"/>
{% endfor %}

---

` How to run a HelloWorld.exe file to use a CMD `
1. windows + R [enter]
2. cmd [enter]
3. Go to HelloWorld.exe folder
4. [project name]  C#  [enter]
5. This exe file is propery good works.

---
`Let's study about HelloWorld code`
{% highlight ruby %}

//Use a System class in System namespace to inform Compiler.
using System;

namespace HelloWorld
{
    class HelloWorld
    {
        //Program start.
        static void Main(string[] args) //Main method
        {
            Console.WriteLine("HelloWorld"); // print out prompt.
        }
    }
}
{% endhighlight %}

[namespace] : namesapce is helped to you about group same class, struct, interface,delegate, enum etc.

namespace + {class is belong to namespace}
---
`What is class?`
class is made up composed data and method as a c# program basic unit.

C# program can compose a lot of classes.

---
`Main method`

Main method is Entry point.

Every program must have a Main method.

---
`static`

staic can modify method and valuable.

static 키워드로 수식되는 코드는 프로그램이 처음 구동 될때 부터 진작에 메모리에 할당 된다는 특징이 있다.

---
[실행 되는 과정]
1. 프로그램 실행
2. CLR (Common Language Runtime)은 프로그램을 메모리에 올린다.
3. Entry point를 찾는데 Main() 메소드가 static이 아니면, CLR은 진입점을 찾지 못함.

컴파일러가 static으로 한정된 Main() 메소드가 없는 경우를 판단 하여 컴파일 에러 메세지 출력

---
`CLR`

Common Language Runtime.
C#으로 만든 프로그램은 CLR 위에서 실행 된다.
CLR은 자바의 자바 가상 머신과 비슷한 역할을 한다.
C# 컴파일러는 C# 소스 코드를 IL(Intermediate Language)라는 중간 언어로 작성된 실행 파일을 만든다.
사용자가 파일을 실행 시키면, CLR이 중간 코드를 읽어 들여 다시 os가 이해 할 수 있는 네이티브 코드로
컴파일한 후 실행 시킨다. 이것을 JIT(Just In Time) 컴파일이라고 부르고 적시 컴파일 이라고도 한다.

CLR은 C# 뿐만 아니라 다른 언어도 지원하도록 설계 되었습니다. 서로 다른 언어들이 만나기 위한 지점이
바로 IL이라고 하는 중간 언어이고, 이 언어로 쓰여진 코드를 CLR이 다시 자신이 설치 되어 있는 플랫폼에
최적화 시켜 컴파일 한 후 실행 하는 것입니다.
이런 방식의 장점은 바로 플랫폼에 최적화된 코드를 만들어 낸다는 것이고,
단점은 실행시 이루어지는 컴파일 비용의 부담 입니다.
CLR은 단순히 C#이나 기타 언어 들을 동작시키는 환경 기능 외에도 프로그램의 오류가 발생 했을때 이를 처리 하도록 도와주는 기능, 언어간의 상속 지원, COM과 상호 운영성 지원, 그리고 자동 메모리 관리 등의 기능을 제공 합니다.

---
`JIT Compile`

실행에 필요한 코드를 실행 할 때마다 실시간으로 컴파일 해서 실행 한다는 뜻이다.
