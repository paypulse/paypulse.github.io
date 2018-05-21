---
layout: post
title:  ".NET Framework"
date:   2018-05-13 10:59:21 +0700
categories: CSharp
---
`.NET Framework`

.NET Framework 는 2002년에 마이크로소프트에서 발표한 응용 프로그램 개발 환경으로서
프로세스 가상 머신에 속한다.

그렇다면, 가상 머신 이란 무엇인가?<br>
`가상 머신`
하드웨어를 소프트웨어 적으로 구현해서 그 위에서 운영 체제가 작동 하도록 하는 기술을 일컫는다.<br>
<br>
<b>그렇다면, 왜? 그렇게 사용 해야 하는데?</b>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/virtualmachin.png" width="320" height="231"/>  
{% endfor %}
<br>
프로세스 가상 머신? 그건또 뭘까? <br>
[출처] : https://ko.wikipedia.org/wiki/가상_머신#프로세스_가상_머신[1]
프로세스 가상 머신들은 플랫폼에 독립적인 프로그램 실행 환경과 추상화를 제공하여 하나의 프로그램을 실행 하도록 설계되어 있다. <br>

일반 네이티브 언어로 만들어진 프로그램들이 운영체제 에서 곧바로 실행되는 것과는 달리, .Net Framework 기반으로 만들어진 응용 프로그램들은 반드시 .Net Framework가 미리 설치된 환경에서만 실행된다.
<br><br>
즉,
