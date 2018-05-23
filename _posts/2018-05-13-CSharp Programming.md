---
layout: post
title:  ".NET Framework"
date:   2018-05-13 10:59:21 +0700
categories: Language
---
`.NET Framework`

.NET Framework 는 2002년에 마이크로소프트에서 발표한 응용 프로그램 개발 환경으로서
프로세스 가상 머신에 속한다.

그렇다면, 가상 머신 이란 무엇인가?<br>
`가상 머신`<br>
하드웨어를 소프트웨어 적으로 구현해서 그 위에서 운영 체제가 작동 하도록 하는 기술을 일컫는다.<br>
<br>
<b>그렇다면, 왜? 그렇게 사용 해야 하는데?</b>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/virtualmachin.png" width="320" height="231"/>  
{% endfor %}
그렇다면, 왜? 가상 머신을 사용 하는건지가 가장 많은 의문이였다.<br>
그냥, 코딩 하고, 실행 파일을 만들어서 배포 하면 되지 왜? 그 실행 파일이나 특정 언어가 가상 머신 위에서 작성 되고, 구현 되어야 하는지에 대해 이해하는게 너무 어려웠다. <br>

그렇게 정보를 찾던 중 그나마 궁금증을 해결 할 수 있었던 출처를 찾았다.<br>
[출처] :https://www.ibm.com/developerworks/community/blogs/9e635b49-09e9-4c23-8999-a4d461aeace2/entry/86?lang=en
<br>

---
VM [Vertual Machine] : 넓은 의미로는 하드웨어로 구현된 실제 컴퓨터나 개념적인 컴퓨터의 소프트웨어 구현을 말한다. Java의 JVM이나 .NET CLR같은 형태의 VM을 일컬어 프로세스 혹은 애플리케이션 VM이라 한다. 위의 출처에 따르면, 프로세스 수준 가상화를 제공하는 VM을 프로세스 VM이라고 통칭하는 대신 JVM같은 VM을 고급언어 VM(high level language VM)으로 통한다. <br>
<br>

---
`고급 프로그래밍 언어란` <br>
사람이 이해하기 쉽게 작성된 프로그래밍 언어 로서, 저급 프로그래밍 언어 보다 가독성이 높고 다루기 간단하다는 장점이 있다.<br>
컴파일러나 인터프리터에 의해 저급 프로그래밍 언어로 번역되어 실행 된다. <br>
<br>
고급 언어의 종류로는    : BASIC, JAVA, 스몰토크, COBOL, Python,C# ... <br>
저급과 고급의 중간 수준 : C,C++ <br>
저급 언어              : Assembly <br>

---
`프로그래밍 언어가 실행되는 원리는 어떻게 되는거지?` <br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/compileEx1.png" width="710" height="196"/>  
{% endfor %}
<br>

많은 수의 컴파일러는 보통 대개 다음과 같은 단계로 나뉘는데 [언어 마다 다르다] <br>
<b>구문 분석 --> 최적화 --> 코드생성 --> 링킹</b><br>
1. 구문 분석 : 소스 코드 파일을 읽어 문법 요소들을 해석 한 후 추상 구문 트리를 생성<br>
2. 최적 화   : 추상 구문 트리를 분석하여, 도달 할 수 없는 코드를 식별 하거나, 상수 표현 식을 미리 계산해 두거나, 루프 풀기 등의 대부분의 최적화 수행 <br>
3. 코드 생성 : 최적화된 구문 트리로 부터 목적 코드를 생성 <br>
4. 링킹      : 목적 코드가 기계어 일 경우, 여러 라이브러리 목적 코드를 묶어 하나의 실행 파일을 생성 하게 된다. 이런 과정은 링커에 의해 수행 된다. <br>

<br>
※링커 : 링커 또는 링크 에디터는 컴파일러가 만들어낸 하나 이상의 목적 파일을 단일 실행 프로그램으로 병합 하는 프로그램 이다. <br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/linkerEx.png" width="585" height="89"/>  
{% endfor %}
<br>

※위의 모든 과정을 빌드 한다고 라고 말한다.<br>
Build : 소스 코드 파일들을 컴퓨터에서 실행 할 수 있는 소프트웨어로 변환하는 일련의 과정

---
`VM 을 사용 하는 이유 ` <br>
[출처에 나온 순서와는 다르다. ] <br>
1. 하드웨어별 특성을 황용 하기 위해 <br>
VM을 사용하면, VM 상의 추상적인 연산을 특정 하드웨어에 포함된 기능을 이용해 더 빨리 수행 할 수도 있다. <br>

무슨 의미 일까? <br>
