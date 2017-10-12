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

` Let's run to HelloWorld.exe file to use a CMD `
1. windows + R [enter]
2. cmd [enter]
3. Go to HelloWorld.exe folder
4. [project name]  C#  [enter]
5. This exe file is propery good works.

---
`Let's study about HelloWorld code`
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
