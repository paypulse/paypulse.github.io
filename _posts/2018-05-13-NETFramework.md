---
layout: post
title:  ".NET Framework"
date:   2018-05-13 10:59:21 +0700
categories: Language
---
<h1> .NET Framework </h1> <br>

`[참조]`
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/csharpBook2.png" width="480" height="626"/>  
{% endfor %}



---
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
예를 들자면, 인텔 SSE2 같은 확장이 있는 플랫폼에서는 해당 명령어를 활용하도록 VM을 구현 할 수 있다.<br>
<br>
2. 플랫폼 독립적인 프로그램 배포를 위해<br>
애플은 매킨토시의 CPU를 파워 PC에서 인텔로 바꿨다. 비록 인텔 기반 맥에서 코드 변환 기능으로 파워 PC기반 소프트웨어를 실행 할 수는 있다지만,
무척 느리고 메모리를 많이 소모한다. 이런 경우 VM을 정의해 VM기반으로 소프트웨어를 배포 했다면, 다시 CPU를 바꾸더라도 별 문제가 없었을 것이다.<br>
<br>
3. 메모리 절약을 위해 <br>
마이크로 소프트 비주얼 베이직에는 p-code엔진이라는 것이 들어가 있다. 이 역시 스택 기계 형식의 VM이었다. 마이크로소프트의 p-code는 크기가 작았는데, 메모리가 모자라던 시절,
속도를 희생하고라도 프로그램 코드가 차지하는 메모리 공간을 줄이기 위한 선택 사항으로 추가 되었다. 버전 5,6 때는 p-code와 기계어 생성 부분을 혼용할 숭 있어서 속도가 불필요한  부분만 기계어로 컴파일 할 수 있게 한다. 이처럼 VM 명령어는 작게 설계할 수 있으므로 메모리가 부족하거나 대역폭이 낮거나 비싼 통신 채널을 통해 프로그램을 전송할때 유리 하다.<br>
<br>
4. 시스템에 입력되는 프로그램의 특성을 제어 하기 위해 <br>
VM코드를 어떻게 정의 하느냐에 따라 자바 처럼 프로그램 실행 전 혹은 실행 중에 코드를 검증하는 것이 가능 하다. 극단적인 예를 들면, VM에 입출력을 위한 명령이 없으면, VM 상에서 돌아가는 프로그램은 입출력을 할 수 없다. 흔히 이런 특성은 자바에서 검증을 통해 자바 코드가 시스템을 깨먹지 못하도록 하는 것 처럼 시스템 안정성이나 보안을 확보하는 방법으로 많이 사용된다. 예를 들면, 최근 휴대폰에 사용되는 JVM은 하나의 메모리 공간에 여러개의 자바 애플리케이션을 동시에 실행 할 수 있는데 이것들이 서로에게 영향을 끼치지 못하는 것은 JVM에 C언어 스타일의 포인터 연산이 없기 때문이다.<br>
<br>
5. 성능을 높이기 위해 <br>
스크립트 언어의 경우 소스 코드를 파싱한 트리를 해석해 가며 동작해서는 성능이 나지 않는다. <br>
고수준 언어로 작성된 프로그램을 실행 하려면 궁극적으로 기계어로 번역해야 하는데 많은 코드가 루프를 가지고 있고 라이브러리 형태로 사용되므로,
한번 실행하고 끝나지 않는다. 따라서 소스 코드에서 기계어 까지 가는 과정 중 반복되는 부분을 최대한 줄여야 만족할 만한 성능을 얻을 수 있다.<br>
이 때문에 소스코드를 기계어에 비교적 가까운 VM코드로 바꿔놓고 반복 사용 하는 것이다. 성능을 높이는 용도로 VM을 사용하는 것은 여기서 그치지 않는데,
자바의 핫 스팟 VM 처럼 정적으로 소스 코드를 분석 해서는 얻을 수 없는 정보를 실행시 수집한 다음 그 정보를 이용해 같은 VM 코드를 더 최적화된 기계어로 변환하는 방법을 사용 할 수 있다. 특히 객체 지향 언어나 동적인 스크립트 언어는 이런 방법을 사용하지 않고는 성능을 개선하는데 한계가 있다. <br>
<br>

6. 컴파일러를 쉽게 구현하고 이식 하기 위해 <br>
초기 UCSD p-시스템의 경우는 말 그대로 컴파일러를 쉽게 이식하기 위해 VM을 도입했다. 특히 스택 기계 형태의 VM은 요즘 CPU 명령 보다 코드를 생성하기가 쉽다. 하지만, 이런 장점은 요즘 처럼 고급 언어를 이용한 개발 등 개발 환경이 좋아진 상황에서는 그다지 의미가 없게 되었다. 심지어 LUA 같은 스크립트 언어는 굳이 코드 생성이 상대적으로 어려운 레지스터 기계 형태의 VM을 사용하기도 한다. 단, 스크립트 언어의 경우 JIT 컴파일 대신 해석기를 쓰는 것이 일반적인데 기계어 대비 성능 저하를 감수 하면서 언어 이식성을 좋게 하는 예라고 볼 수 있다.<br>

---
<div class="blueFont">
[내가 한 이해] :
</div>
내가 이해 한건 하드웨어의 특성에 굳이 맞추지 않아도 VM을 이용해 접근 할 수 있고, VM 기반으로 소프트웨어를 개발하고 배포 했다면, CPU에 상관없이 동작 할 수 있다.<br>
VM 명령어는 많은 메모리 공간을 차지 하지 않기때문에 프로그램 전송시 유리 하다. 등등... <br>

---
따라서, 닷넷 프레임 워크는 응용 프로그램 개발 환경으로서, 프로세스 가상 머신에 속하니, 닷넷 프레임 워크 기반으로 만들어진 응용 프로그램은 반드시 닷넷 프레임 워크가 미리 설치된 환경에서만 실행이 된다. <br>

윈도우 10 크리에이터 버전에서는 닷넷 프레임워크 4.7이 기본적으로 탑재 되어 있다. <br>

---
<h2>CLR</h2><br>
Common Language Runtime <br>
닷넷 프레임 워크를 설치하면, 닷넷 프레임 워크의 가상 머신인 CLR이 설치되어, 닷넷 프레임워크 기반으로 만들어진 응용 프로그램을 실행 될 수 있는 환경이 윈도우 운영체제에 마련된다.
<br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/netFrameT1.png" width="700" height="234"/>  
{% endfor %}
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/netFrameT2.png" width="700" height="199"/>  
{% endfor %}
<br>
사용자가 C#으로 개발된 어플리케이션을 실행하면, 내부적으로 컴파일러에 의해 생성된 CLR이 로드 되고, CLR은 IL코드를 로드해서 실행 한다.

---
<h2>닷넷 호환 언어</h2><br>
IL과 같은 중간 언어는 어느 하나의 프로그래밍 언어에 종속된건 아니다.<br>
CLR은 언어에 상관없이 컴파일러에 의해 만든 중간언어를 실행 할 수 있다. <br>
<div class="blueFont">
중간 언어로 번역하는 언어를 닷넷 호환언어 (NET-Compliant Language)라고 하며, C#언어는 단지 그러한 언어중에 하나일뿐이다.
</div><br>

<div class="redFont">
닷넷 호환언어의 장점 :
</div>
 중간언어[IL] 코드의 결과물을 공유 하기 때문에, 상호 호출이 가능하다.
- C#으로 만든 코드를 F#에서 사용 할 수 있고, 심지어 다른 언어로 만든 클래스 까지도 상속 받을 수 있다.<br>

---
<h2>공통 중간 언어</h2><br>
자바 VM의 중간 언어 : 바이트 코드 (Byte code)<br>
닷넷 CLR에서 중간 언어 :CIL (Common Intermediate Language)라고 한다. <br>
이를 줄여 IL 코드 OR MSIL 코드라고 한다. <br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/comLanguage.png" width="1420" height="286"/>  
{% endfor %}

---
<h2>공용 타입 시스템</h2><br>

CTS :Common Type System  <br>
닷넷 호환언어가 지켜야할 타입의 표준 규격을 정의한 것이다. <br>
(if): 새로운 언어를 만들어 닷넷 프레임워크 상에서 실행 하고 싶다면, CTS규약 한도내에서 구현 할 수 있다.<br>
즉, 닷넷 호환 언어는 CTS의 한계를 넘어 구현 할 수 없다. <br>
C#과 Visual Basic, .Net 언어는 CTS가 정의한 타입 시스템의 일부를 자신들의 언어 사양에 맞게 구현 하고 있다.<br>

<div class="blueFont">
만약 , CTS전체를 활용해 프로그램을 만들고 싶다면, IL언어를 사용하거나 CTS 전체 규격을 표현한 언어를 새롭게 만들어야 한다.
</div><br>

---
<h2>공용 언어의 사양</h2><br>

CLS : Common Language Specification <br>
닷넷 호환 언어가 지켜야할 최소한의 언어 사양을 정의 한 것이다. <br>
(if) 직접 닷넷 호한 언어를  만들고 싶다면, CTS 전체를 구현할 필요는 없지만, 적어도 CLS에 명시된 사양만큼은 완벽하게 구현 해야 한다. <br>

(ex) C#에서는 부호 없는 형식을 지원 한다. 이는 CTS에 정의 돼 있기 떼문에, C#에서도 정의 할 수 있다. <br>
하지만 CLS에서는 unsigned 타입을 강제화 하지 않았다. 이는 C#에서 unsigned 타입이 구현 됐다고 해서 다른 언어 에서도 unsigned 타입이 구현 됬다고 보장 할 수 없다. <br>

<div class="redFont">
닷넷 호환 언어 끼리는 서로 사용 할 수도 있고, 상속 받을 수도 있다.
</div><br>
C# 언어 에서 unsigned 타입을 사용하는 함수를 정의 했다고 가정 했을때, unsigned를 지원하지 않는 다른 언어 에서 이 함수를 사용하면, 호환성 문제가 발생 하게 된다. 그렇기 때문에 타 언어와 섞는 프로그램을 만들때, 외부에서 사용할 기능에 대해서 CLS를 준수 해야 한다. <br>

<div class="blueFont">
CLS의 두가지 측면 : <br>
1. 모든 닷넷 호환 언어가 CLS에서 정의한 사양 만큼 구현해야 한다. <br>
2. 닷넷 호환 언어 끼리 호출해야 하는 경우 그 기능에 한해서 CLS를 만족 시키도록 작성 <br>
</div>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/ctsandcls.png" width="318" height="340"/>  
{% endfor %}
<br>

---
<h2>Meta Data</h2><br>
"누구 누구씨 그 파일 메타 데이터 가지고 와 !"<br>
<div class="blueFont">
데이터를 위한 데이터를 의미 한다.
</div><br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/mataEx.png" width="426" height="584"/>  
{% endfor %}
QNAmaker.png라는 이미지 데이터 안의 데이터의 너비, 높이 등의 데이터가 메타데이터에 해당한다. <br>

<div class="redFont">
프로그래밍 언어에서 개발자가 구현한 코드가 데이터에 해당하고, 해당 코드의 성격을 설명해주는 별도의 데이터를 메타데이터라고 한다.
</div><br>

CLR에서 동작하는 실행 파일은 메타 데이터를 제공 하고 있으며, 외부에서는 이러한 정보를 Reflection이라는 기술을 통해 사용 할 수 있다.<br>

C#언어로 컴파일된 EXE/DLL 파일에도 메타데이터가 담겨 있다. 찾아 보자! <br>
아.. 난 2일 동안 잘못 찾고 있었다. exe/dll의 메타데이터를 찾을것이 아니라. 리플렉션에 대해서 자세히 봤어야 했다. <br>

[출처] : http://www.csharpstudy.com/Practical/Prac-reflection2.aspx <br>

Reflection과 Attribute는 함께 정리 되어야 하기에 일단 Check <br>

---
<h2>Assembly, Module, Menifest</h2><br>
C#으로 프로그램을 만드는 경우 대개 EXE 또는 DLL 파일을 만들게 된다. <br>
<div class="redFont">
  기계어와  1:1 대응 되는 프로그래밍 언어인 어셈블리와 이름이 같으므로, 혼동할 수 있지만, 닷넷 프로그래밍 에서 특별한 언급이 없다면, 어셈블리는 실행 파일 (EXE,DLL)을 의미 한다.
</div><br>

{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/assembly1.png" width="682" height="394"/>  
{% endfor %}
<br>

이렇게 여러개의 파일이 하나의 어셈블리를 구성하고 있다면, 여러 파일을 목록으로 만들어 관리할 필요가 있다.이를 위해 모듈중 하나는 반드시 다른 모듈의 목록을 관리하는 메니페스트 데이터를 담고 있어야 한다.<br>
<br>
<div class="blueFont">
netmodule  : 메니페스트 데이터를 포함하지 않는 모듈
</div><br>
보통 위의 그림 처럼 다중 모듈을 사용하는 경우는 거의 없다. 어셈블리 [exe/dll]에는 메니페스트 데이터를 포함하고 있다. <br>

---
<h2>공용 언어 기반구조</h2><br>
공용 언어 기반구조 (CLI : Common Language Infrastructure)는 마이크로소프트에서 ECMA 표준으로 제출한 공개 규약이다. CLI, CTS 명세를 포함 하고 있으며, 중간 언어에 대한 코드 정의, 메타데이터와 메타데이터를 포함하는 이진 파일의 구조까지 표준 사양으로 기술 하고 있다. <br>

{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/cliandClr.png" width="508" height="534"/>  
{% endfor %}
<br>
CLI 규격을 마이크로소프트에서 구현한 실체가 바로 CLR이다. <br>

---
<h2>공용 언어 런타임</h2><br>
CLR 은 CLI사양을 따르는 가장 대표적인 VM으로서 마이크로소프트가 개발해 윈도우 운영체제용으로만 배포되고 있다.<br>

<div class="blueFont">
CLR에는 두가지 큰 기능 :
</div>
1. 중간 언어를  JIT compiler를 이용해 기계어로 변환한다.<br>
2. 가비지 수집기(GC :Garbage Collector)를 제공해 동적 메모리 할당 및 회수를 지원 <br>

`JIT compiler란?` <br>
[참고] :https://ko.wikipedia.org/wiki/JIT_%EC%BB%B4%ED%8C%8C%EC%9D%BC <br>
wiki에 나와 있는데로, JIT (Just In Time) 컴파일러 또는 동적 번역은 프로그램을 실제 실행 하는 시점에 기계어로 변역하는 컴파일 기법이다. 이 기법은 프로그램의 실행 속도를 빠르게 하기 위해 사용된다.<br>

CLR은 프로세스내에서 공개된 API에 의해 로드될 수 있다. <br>
즉, 윈도우 개발 환경에서 동작하는 기존 네이티브 응용 프로그램에서 CLR을 내장하는 것이 가능하다. <br>

CLR을 로드 하는 w3wp.exe : 윈도우에 포함된 웹 서버인 IIS(Internet Information Services)는 기존의 w3wp.exe 프로세스에 CLR을 자동으로 로드할 수 있는 기능을 추가 했다. 이로써 개발자는 명시적으로 CLR을 로드 하는 코드를 작성 하지 않고도 웹 어플리케이션을 닷넷언어로 만들 수 있다.<br>

CLR을 로드하는 SQL 서버 :마이크로 소프트의 SQL 서버는 CLR을 로드해서 내장 프로시저를 작성 할 수 있게 한다. 또한 데이터 베이스의 테이블에 포함되는 칼럼의 타입을 닷넷의 클래스로 확장 할 수 있다. <br>

CLR을 로드하는 인터넷 익스플로러 :웹 브라우저인 IE(Internet Explorer)도 CLR을 로드 하기 때문에 닷넷 호환언로 만들어진 컨트롤을 웹 브라우저에서 활성화 할 수 있다. <br>

CLR을 로드 하는 셀(Shell)명령어 : 도시 시절의 배치 명령어를 기반으로 한 명령행 셀이 윈도우 에서도 제공되지만 기능 면에서 너무 제한 적이다. 마이크로소프트는 닷넷 프레임 워크를 출시하면서 파워셀을 별도로 제공하기 시작 했는데. 이 새로운 명령어 해석기에는 CLR이 기본적으로 로드돼 있어 닷넷용으로 만들어진 명령어를 사용 할 수 있다.<br>

CLR 자체를 관리 환경이라고 하고, CLR이 로드 되는 프로세스를 기존의 네이티브 프로세스와 구별해 관리 프로세스라고 한다. <br>
