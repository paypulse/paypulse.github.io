---
layout: post
title:  "1.Hello, World!"
date:   2017-10-08 10:59:21 +0700
categories: CSharp
---
`Hello, World`

I used a visual studio 2012 version IDE.
{% highlight ruby %}
using System;

namespace HelloWorld
{
    class HelloWorld
    {
        //프로그램 실행이 시작 되는 곳
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

`Window 탐색기를 실행해서 실행 파일이 제대로 생성 되었는지 확인 해 보자. `
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/helloworldExe.png" width="779" height="208"/>
{% endfor %}

---

` IDE ctrl + f5 가 아닌  명령 프롬프트에서 HelloWorld.exe를 실행 `

1. windows + R
2. cmd
3. HelloWorld.exe가 있는 경로로 간다.
4. [project 명]  C# 을 입력 해야 예제 실행 파일이 정상적으로 실행이 된다.
