---
layout: post
title:  "GoogleExtended I/O 2018"
date:   2018-06-10 10:59:21 +0700
categories: SUS
---
<h1>GoogleExteneded I/O</h1><br>

---
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/googleSeminar.png" width="480" height="626"/>  
{% endfor %}
<br>

늦은 줄 알고 서둘러 11시까지 왔는데 다행히 늦지 않았다. 잠 좀 줄이자.
Track A, Track B, Track C 로 나뉘어서 강의를 진행 한다.
Track A는 안드로이드 관련 인것 같았고, Track B는 TensorFlow 같았고, Track C는 웹앱관련 강의 같다. <br>
여러가지를 섞어 들을 필요가 있다. 듣고 싶은 주제를 마음대로 옮겨가면서 듣다 보니 정말 강의들이 지루하지 않고 너무 신선 하다.<br>

그래도 이런데 와서 세미나를 들으면서 느낀점은 그래도 지금 하고 있는 공부 방향이 다행 스럽게도 미래 지향 적이라는걸 깨달았다. <br>

그냥 꾸준히 그대로 진행 하고, 개발하자. <br>

구글에서 티셔츠도 주고, 선그리도 주고, 스티커도 주고 ㅋㅋㅋ올해 목표가 꼭 이루어지게 노력하자. 열심히 뼈를 깍는 고통을 감내 할 줄 알아야 작은 성과에도 큰 감동이 몰려 온다. ^_^ 열심히 하자.<br>

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

Android Auto<br>
1. 메시징 앱 - 음성만으로 메세지를 확인하고 답장을 할 수 있다.<br>
2. 미디어 앱 - 구글 어시스턴스를 통해 어플 사용이 가능하다. <br>
<br>
어시스턴스를 사용해서 검색할 수 있는 기능이 추가 되었다.<br>
참 좋은 세미나다. 이러한 기능을 사용 하고 싶다면, Google API를 찾아서 쓰세요. <br>
데스트탑 헤드 유닛의 기능을 제공하고있다. <br>
TV는 역시 컨텐츠! <br>
컨텐츠 1st UX란?<br>
홈안에서 모든 내용을 확인 하고, 바로 플레이 할 수 있게 , 사용자가 쉽고 빠르게 컨텐츠를 선택하고 파악할 수 있게 제공을 해주고 있다 <br>
채널의 이름과 로고를 구성하기 위한 함수를 제공 하고 있다. <br>
안타 깝다. 이렇게 사용하기 쉽게 API 모두 제공해서 사용 할 수 있다는게, 솔직히 이런 API 직접 개발해서 사용해야 하는건 아닌지 싶다. 그게 진짜 프로그래머지.<br>

구글 어시스턴트를 이용해서 구글 TV에서 검색을 하면 컨텐츠에 대한 다양한 정보가 제공이 된다. <br>

위의 모든건 구글 어시스턴트에 모두 나와 있다.<br>

android wear by google update<br>
Stand by buket?<br>
머신러닝 기능을 제공 하고 있다. <br>
<br>
코틀린 DSL을 이용한 간편한 위치 페이스 개발 <br>
앞으로 나올 예정이다. 현재는 구현 중이다. <br>
600라인을 15라인으로 구현 될 수 있다. <br>

1. 안드로이드 Auto 업데이트 - 메세징 구현, 미디어 탐색 기능, 검색 기능 구현 <br>
2. content's 1st UX <br>
3. wear에서는 어떻게 배터리 성능을 구현할지 <br>
4. 코틀린 DSL <br>

해당 강의에 관한 google utube 동영상이 있다. <br>


---
<h2>모바일 개발자를 위한 머신러닝</h2><br>
[강사] :남상균, NBT <br>

우리에게 머신러닝이라면 엄청 나게 먼 느낌이 들지만,이젠 Google에서 API를 지원해주나 보다.<br>
Mobile first to AI first <br>
Mobile은 Default고 AI를 구축해야 한다. <br>

Solving problems with AI for everyone.<br>

Deep learning Vs machine learning 기술이 굉장이 Hot해졌다. <br>

TensorFlow<br>
Deep learning and machine learning을 쉽게 구축하기 위해 <br>

On-Device ML의 필요성 <br>
낮은 지연시간, 서버 호출 없음, 오프라인에서 동작 기능, 데이터가 디바이스 측게 보관,... <br>
하지만, 메모리 사양에 제약이 있거고, 컴퓨팅 타워가 적고, 배터리 소모를 낮추기 위해 에너지 절감 <br>

Apple에 Core ML모델이 있다. <br>

TensorFlow Light <br>
모바일에 특화된 경량화된 Model이다.<br>
학습보다는 추론만 가능하게 구현할 수 있다. <br>
플랫폼에 상관　없이 사용 할 수 있다. <br>

ML KIT <br>
서비스 하기 힘들었던 TensorFlow Light의 단점을 보안하기 위한 서비스이다. <br>
Firebase 위에 올라가서 개발해진다.
하지만, ML Kit은 프로젝트를 올려서 쉽게 구현 할 수 있게 되어 있다. <br>
Android, IOS 모두 지원 하는 장점이 있다. 기본 API와  커스텀 모델 <br>

기본 API <br>
1. 이미지 라벨 지정 <br>
2. 텍스트 인식 <br>
3. 얼굴 감지 : 감정도 표시를 해준다. <br>
4. 바코드 스캔 <br>
5. 랜드마크 인식 <br>
6. 스마트 회신 (제공 예정) <br>

커스텀 모델 <br>
1. 동적 모델 다운로드 : 파이어 베이스를 이용해서 <br>
2. 파이어 베이스 원격 설정을 통한 A/B 테스트 <br>
3. 모델 변환과 압축 (제공 예정) <br>

실제 ML Kit이 어떻게 동작하는지는 직접 돌려 보는게 중요하다 <br>
기본 API 구성 방식에는 On-device냐 Cloud냐로 나뉘어져 있다 <br>
이 위의 모든것을 수행하려면 Firebase와 연결이 되어 있어야 한다. <br>
On-device보다 cloud가 더 많이 표현 할 수 있지만, 비용이 든다 <br>

핸즈온은 절대 어렵지가 않다. <br>
※ ML Kit는 반드시 Firebase 안에서 돌아간다. <br>

ML KIT 은 변곡점이다. <br>
이제 모바일에 AI를 추가 하는 것이 굉장히 간다하고, 쉬워 졌다. <br>
사용자에 능동적으로 다가가기에 변곡점에 해당한다.<br>
ML Kit을 이용해 좋은 서비스를 많이 만들자<br>

<div class="blueFont">
그렇구나. 뭐가 어려워 참... 구글이 다 해주는데...구글이 개발자고 나머지는 그냥 코더지 설치 복붙해! <br>
그러니까 쫄지 말자. 이런 지원 해주는 API나 플랫폼에 의존하지 말고 개발하는 개발자가 되어야 하는데 <br>
꼭! 돌려 보자
</div><br>

---
<h2>Microservices in the Cloud with Kubernetes Istio</h2><br>
[강사] :이정운, Google <br>

Microservice란?<br>
서비스 단위로 어플리케이션 구성, 서비스는 독립적으로 배포 일 확장 가능<br>

MSA란?<br>
MicroServices Architecture<br>
장애를 고려한 설계<br>
각각의 DB에 분산 데이터 관리를 해야 한다.<br>
어떻게 이 MSA를 효율적으로 관리 할것인가? <br>
<br>
다양한 시도 <br>
1. Spring Cloud 를 만든다. <br>
2. Spring Cloud Neffrix를 이용한다. <br>

Docker<br>
쉽게 vm으로 보면 된다.<br>
code를 container로 본다<br>
docker의 문제점을 해결하기 위해 Kubernetes를 사용 한다.<br>
<br>
Kubernetes - container Orchestration<br>
code -> container -> Orchestration ---> 이렇게 해주는게 Kubernetes라고 한다. <br>

Service Mesh<br>
커뮤니케이션을 보다 안정적이고 안전적으로 관찰하고 관리가 가능하게 하기 위하여 서비스간 커뮤니케이션 을 처리 하는 기능이다. <br>
[구현된 제품] : Istio
Istio<br>
Orchestration ->Management and Communition <br>
이게 Service mesh가 하는 역할이다. <br>

Sidecar 패턴 <br>
서비스 프록시가 필요 하고, sidecar 패턴 형태로 배포 할 수있다. <br>
코드를 다시 작성하거나. 아키텍처 변경없이 배포 할 수 있다. <br>
어플리케이션 개발자가 실제 운영에 대한 개념을 가지고 있어야 하는게 그것이 service mesh에 해당한다.

어플리케이션과 인프라의 분리 <br>
어플리케이션에는 정말 필요 한로직이 있고, 운영에 관한것들을 service mesh라고 한다. <br>
개발에서 운영의 결합을 제거 하는것이다.<br>
운영에 장애가 났을때 어떻게 처리 할 것인지를 끊어 내자는것이 service mesh에 해당한다.<br>
코드를 변경하지 않고 서비스 동작및 트래픽 흐름을 변경하자. <br>

정확히 각각의 Role에 맞게 개발 하자는것이 service mesh가 가진 장점에 해당한다. <br>
sidecar pattern으로 설정이 들어 가고, Application을 바꾸지 않아도 Microservice를 할 수 있다. <br>

아... 이번건 좀 어려웠다. Docker에 대해 말만 들어 봤지. 거의 사용해본적이 없는데 그래도 중요 한건, 그냥 Google Service를 써라... 이런것 같다. 심지어 모니터링까지. <br>
직접 서비스에 추가할때 좀 위험하지 않을까 싶다. 돈이 필요 하겠지 흠... <br>
