---
layout: post
title:  "GoogleExtended I/O 2018"
date:   2018-06-10 10:59:21 +0700
categories: SUS
---
<h1>GoogleExteneded I/O</h1><br>

---
늦은 줄 알고 서둘러 11시까지 왔는데 다행히 늦지 않았다. 잠 좀 줄이자.

Track A, Track B, Track C 로 나뉘어서 강의를 진행 한다.


---
<h2>Key note</h2><br>

[강사] : David MacLaughlin <br>

Developer Relations<br>
Open Source is a key part of Google Engineer<br>

GDG <br>
Google Develper Group<br>

Google Developer Experts<br>

communiti를 중시 하는데 Woman techmakers <br> 찾아 봐야 할것 같다.<br>

meetup 에 GDG에서 관심있는 chapter의 이벤트및 세미나를 알 수 있다.<br>

[GDG Slack] <br>
slack.gdg.kr<br>

---
<h2>Exploring what's new in Web for the Natively app</h2><br>
[강사] :도창욱 , Riot Games <br>

(모바일) 웹을 만들려면!! 어떻게 렌더링 퍼포먼스를 높일 수 있을지.<br>
The service worker - 브라우저와 OS 사이에서 동작하는 백그라운드 기능 <br>
웹 페이지 밖, 이벤트와 네트워크를 프록시 처럼 처리 한다. <br>

웹앱이 마치 디바이스에 설치 된것 처럼 네트워크가 끊어진 상황에서도 사용이 가능하게 되어진다. <br>
약간 하이브리드앱 같은 느낌이다. <br>
Romote Push Notification <br>
Background Sync - 네트워크가 사용이 가능할때, 이전에 처리 못한 저장한 이벤트를 처리 할 수 있다. <br>
즉, service worker로 인해 네트워크가 없더라도 메신저 기능을 구현 할 수 있게 된다. <br>

Mobile web <br>
Mobile device의 트래픽이 엄청 난다.<br>

Service worker and web manifest <br>
Progressive web app -  기술이 아닌 마케팅을 위한 단어?, 궁극적으로 웹앱의 지향성을 모아놓은 마케팅 세일즈에 불과 하다.  <br>

PWA - 신뢰성, 빠르고, 사용자가 필요한 정보를 빠르게 접근 할 수 있는 Engaging<br>
컨텐츠가 안정적으로 전달하기 위해 https , 기본적으로 서비스들은 빠르게 동작이 되어야 한다. <br>

모바일, 네트워크가 잘 안되는 지역을 위해 만들어진 기능들이다. <br>

Offline Wep App <br>

user Engagingment <br>
일반 네이티브 앱처럼 만드는. . . 사용자가 브라우저에서 즐겨찾기 한것들이 빨리 뜨는 <br>

web menifest<br>
시스템에서 menifest만 보고 기술하는게 중요 하다.

App Install banner <br>
모바일 웹에 tool bar 같은 기능이다. <br>

Web Assembly<br>
Realworld Examples <br>
web browser상에서 동작하는 저수준의 instruction set을 정의 <br>

다른 언어로 만든 구현물을 웹으로 바꿔야 하는 경우, web assembly를 이용해서 web으로 바꿀 수 있다 <br>

Web Media <br>l
Picture in Picture <br>
ex) 페이스북 동영상 실행시 drag 햇을때 나오는 <br>

Presentation API <br>
파워 포인트, 키노트, 여러 스크린이 있을때, 각 스크린에 다른 컨텐츠를 띄어 놓고 컨트롤 가능하게 하는 <br>

Media Capability<br>

Trasted web activate <br>
기존의 web view나  custom tab을 사용하는데, 네이티브 앱을 같이 구현해야하는 <br>

WorkBox를 사용하면 굉장히 편하다. <br>

Native App Install Banner <br>
App Indexing - 네이티브 앱 개발자 구현할건데... <br>
엄청 빠르다. 녹음 하길 잘했네....<br>

네이티브와 웹이 동등한 현실이다. <br>

---
<h2>웹의 미래는 몰입형 -WebVR 및 WebXR</h2><br>
[강사] :맹기완, 비사이드 소프트 <br>

Immersive web : Virtual Reality, Augumented Reality<br>
오늘은 Virtual Reality만 다룬다 <br>

1. VR의 개념이 있다. <br>
VR과 AR을 결합한것을 Web에서 보여 줄 수 있다 -->Immersive Web이다 <br>

WebVR<br>
이미 웹 브라우저에 탑재 되어 있다. <br>
웹 VR표준만 준수하면 서비스 런칭을 가능하다. <br>
Web VR, Game potal을 많이 구현하고 있다. <br>

WebXR <br>
new Immersice new VR <br>
AR, VR을 다 지원하는 API이다.<br>
보다 다양한 기기에서 같은 코드 한방에 모두 구현 가능 할 수 있게 <br>
일관된 API에서 훨씬 구현하는데 편하게<br>

가장 중요한건 최적화이다. <br>
최적화의 핵심은 2배 많은 픽셀을 그래픽 컨텐츠를 볼 수 있게 해준다.<br>
파이프라인이 넓어지고 전송률이 좋아지기 때문에, 좋은 화면을 구성 할 수 있다. <br>


chrome://flags/#webxr 에서 확인 가능하다. <br>

Building with webxr <br>
1. Detecting :<br>
2. XRSession :requestSession 함수에 대한, <br>
3. XRView and Input :<br>
4. Magic Window <br>
5. Polyfill :www.github.com/immersive-web/webxr-pollyfill <br>

새로운 스펙들은 navigator에서 구현 가능하다. <br>
WebGL에 대한 지식이 필요 ㅋㅋㅋ,webGL은 기본이다. <br>


---
<h2>안드로이드 P 업데이트 - Auto, TV, Wear</h2><br>
[강사] :김원일, Google<br>






---
<h2>모바일 개발자를 위한 머신러닝</h2><br>
[강사] :남상균, NBT <br>




---
<h2>Microservices in</h2><br>
[강사] :
