---
layout: post
title:  "Unity3D로 게임 만들자 1탄"
date:   2018-05-25 10:59:21 +0700
categories: SPP
---
<h1> Small project : 3D Shooting Game </h1> <br>

---
`[참조 책]` <br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/unityBook.png" width="444" height="550"/>  
{% endfor %}
<br>

자.. 그럼 이제 시작 해 볼까?

---
<div class="redFont"> 최종 목표 : SNG 3D액션 게임을 만들어서 App Store에 런칭 하기!
</div><br>

---
<h2>Chapter 01. 게임 개발 순서 </h2><br>

첫번째 예제는 Shooting 게임 개발이다. <br>
`Shooting 게임 이란?` <br>
[출처] : https://ko.wikipedia.org/wiki/슈팅_게임 <br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/shootingEx1.png" width="391" height="338"/>  
{% endfor %}
<br>
이 책에서는 게임 개발을 크게 다음과 같은 순서로 진행 한다. <br>
1. 게임 개발 환경 설정 <br>
2. 게임에서 사용할 리소스 내려 받기 및 설치 <br>
3. 게임의 배경이 되는 스테이지 제작 <br>
4. 주인공의 이동 및 공격 기능 구현 <br>
5. 적 캐릭터 생성 및 추적 기능 구현 <br>
6. 주인공과 적 캐릭터 간의 공격 및 피격 기능 구현 <br>
7. 인벤토리 UI 및 데이터 저장 <br>

---
1. 게임 개발 환경 설정 및 리소스를 내려 받자. <br>
<br>
프로젝트 명 : SpaceShooter <br>
Template   : 3D 모드 <br>

Unity 화면 배치는 자유롭게 해도 되지만, 책에서는 2by3 레이아웃으로 바꿔서 진행 한다.<br>
프로젝트 뷰를 개발 처음 부터 체계적으로 관리 하는것이 프로젝트를 효율적으로 관리 하는 방법중 하나이다 <br>
<br>
책에 나온 폴더 명칭과 분류 기준을 사용 할 예정이다. 왜냐면, 너무 정리가 잘 되있어서 <br>
그런데 전에 절대 경로가 있었던것 같았는데. 어쨌든 잘 정리 된것 같다. <br>
<br>
01. Scenes : 씬을 저장 한다. <br>
02. Scripts: C# 스크립트를 저장한다. <br>
03. Prefabs: 프리팹을 저장한다. <br>
04. Images : 텍스쳐 이미지 및 머티리얼을 저장한다.<br>
05. Models : 3D 모델을 저장한다. <br>
06. Sounds : 오디오 파일을 저장 한다. <br>
07. Animations : 애니메이션 컨트롤러 및 각종 애니메이션 클립을 저장한다. <br>

<br>
`캐릭터 모델을 임포트 하자!` <br>
<div class="blueFont">Git Hub 저장소에서 다운 받자 :
 git clone https://github.com/IndieGameMaker/UnityBook
</div><br>
아.. 그런데 왜이렇게 오래 걸리지? 내 성질이 급한가? 다운로드 후! <br>
<div class="blueFont"> UnityBook  -> Resources -> Models -> Player
</div> Player 패키지를 프로젝트안에 Import 시켜 준다. <br>

<div class="redFont">
  ※ 유니티 패키지 오류 : 유니티 패키지가 설치가 되지 않는다면 <br>
  1. 유니티가 실행 (Run) 모드 이다.<br>
  2. 유니티 패키지 파일이 저장된 경로에 한글이 포함되어 있을때.
</div><br>

<div class="blueFont">
에셋 스토어에서 Skybox Volume2 다운로드 후 임포트 하자. 무료다 !
</div><br>
임포트 후에 Images 폴더에 옮겨 준다.<br>

---
2. 게임의 배경이 되는 스테이지 제작!<br>

예전에는 Box를 가지고 했던 기억이 있지만, Quad 모델을 사용 한다. <br>

Quad란?<br>
[사전적 의미] : 여러가지 의미가 있으나, 4인실, 4개짜리 물건을 의미 한다. <br>
Quad model은 2개의 삼각형 , 4개의 정점으로 구성된 단순한 3D 모델이다. <br>

<div class="blueFont">Quad를 배치 한다 !!
</div><br>

※Transform 컴포넌트의 Position, Rotation 속성 <br>
`Position`<br>
X : 0, Y : 0,  Z : 0 <br><br>
`Rotation`<br>
X : 90, Y : 0, Z : 0 <br>
`Scale`<br>
X : 50, Y : 50,Z : 50 <br>

씬뷰에 배치된 모든 게임 오브젝트(GameObject)의 이름은 직관적인 이름으로 바꿔야 편하다. <br>
폴더명, 프로젝트 명, 변수명도 알아 보기 쉽고, 직관적인 이름이여야 나중에 바꾸거나 고치기 쉬운거랑 같은 맥락이다.
<br>

<div class="blueFont">현재 Quad를 Floor란 이름으로 바꾼다.
</div><br>

<b>Capsule</b>을 추가 해준다. <br>
Capsule을 생성하고 Capsule의 <b>Position</b>의 속성을 (0,1,0)으로 설정 한다.<br>

Capsule이 사람이라고 본다면, Quad는 지형에 해당 되겠지? <br>

---
<h2>Texture</h2><br>
텍스쳐란?<br>
3D 모델의 표면에 매핑 시킬 이미지 파일을 지칭 한다.<br>
[출처] : https://3dscanexpert.com/3d-scan-uv-texture-remap-c4d/ <br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/TextureEx.png" width="444" height="265"/>  
{% endfor %}<br>

유니티는 텍스처의 원본을 보존한 상태로 다양한 압축 포맷으로 용량을 줄이는 기능을 제공 하므로 원본 텍스트를 불러와 사용 할 수 있다. <br>

<h2>※ 텍스처는 가로와 세로의 크기가 2ⁿ 형태일때 압축을 지원 하며 속도가 빠르다.</h2><br>
<div class="redFont">
  특히! 모바일 플랫폼에서 속도를 향상 시키고 싶다면 반드시! 2ⁿ(POT : Power Of Two)
  형태의 텍스처를 사용해야 한다.
</div><br>

<h2>텍스쳐 임포트</h2><br>
지난번에 Git에서 다운 받은 리소스 <br>
<div class="blueFont">
  Resources -> Texture -> Stages 폴더를  04.Images폴더로 옮긴다.
</div> <br>
Drag and Drop ---> 끝 <br>

<h2>텍스처의 해상도 조절 </h2><br>
모바일 플랫폼 출시를 하려면, 반드시 텍스처의 해상도를 적절히 줄여야 한다. <br>

floor 이미지의 해상도는 1024 × 1024 이고, 크기는 1.3MB 이다. 그래서 해상도를 적절히 줄일 필요가 있다. <br>

책에서는 256으로 설정 하라고만 했지, 왜? 설정하라고 하는지는 안적혀 있다.<br>

<div class="blueFont">
  floor 텍스처 해상도 --> 256으로 바꾸기
</div>

<div class="redFont">
  프로젝트가 진행되면서 임포트하는 텍스처는 바로 적절한 품질로 설정하는 작업을 병행해야 나중에 최적화 작업에 유리 하다.
</div>

---
<h2>Material</h2><br>
머티리얼은 3D 모델에 적용할 텍스처의 다양한 속성을 설정하는 역할을 한다. <br>

<div class="blueFont">
  floor 텍스처를 scene 뷰에 있는 Quad모델인 Floor에 Drag and Drop 해준다.
</div><br>

Drag and Drop 해줌과 동시에 Material 폴더가 생기고 floor 머티리얼이 생긴다.<br>

이렇게 Drag and Drop 해주면 편하겠지만, 텍스처가 늘어 나면 늘어 날 수록 관리 하기가 불편해 진다. <br>

Materials 폴더를 만들고, 빈 material을 만들어 준다.<br>

<div class="blueFont">
  빈 Material -> Albedo 에 Texture를 연결 해준다.
</div>
이렇게 해준 Material을 3D 객체 입혀 준다.<br>

`타일링 속성`<br>
머티리얼 기능 가운데 텍스처를 욕실의 타일처럼 반복 시키는 기능이 있다. <br>

타일링 속성은 Main Map 색션의 Tiling 속성을 수정해야 한다.<br>
Secondary Map 색션의 타일링은 3D 모델의 특정 부분을 좀 더 세밀하게 표현하기 위한 텍스처가 적용되는 영역이다.<br>

---
<h2>셰이더 및 물리 기반 셰이딩</h2><br>

셰이더는 머티리얼에 적용한 텍스처를 렌더링 할 때 표면의 재질감을 표현하는 방식을 결정 한다.<br>

셰이더 프로그래밍은 DirectX, OpenGL에 따라 서로 다른 언어로 구현되고, 3D 그래픽스의 이론적인 배경을 많이 알아야 할 정도로 깉이 있는 지식을 요구하는 분야이기도 하다. <br>

셰이더 프로그래밍 어려운건가? <br>

유니티는 이런 어려운 지식이나 경험 없이도 손쉽게 사용 할 수 있다. 왜냐? 유니티는 게임 엔진이니까. 누구나 쉽게 게임을 만들 수 있게 하기 위해 이런 기능들이 모두 내장 되어 있다.<br>

유니티의 기본 셰이더인 Standard 셰이더는 물리 기반 셰이딩을 위한 다양한 옵션을 제공한다.<br>

머터리얼의 어려가지 파라미터가 존재 한다.
유니티 Standard 셰이더에 대한 세부 정보 : https://docs.unity3d.com/Manual/shader-StarndardShader.html <br>

메뉴얼을 참조 하자!!

---
<h2>프리팹</h2><br>
나는 자꾸 프리팹의 개념이 마치 클래스의 개념과 같은것 같다.<br>

유니티에서의 프리팹은 복사가 가능한 원본의 개념으로, 프리팹을 복제해서 만든 복사본의 속성은 원본의 속성과 일치 한다. 따라서 원본 프리팹을 수정하면 그 복사본은 수정사항이 자동적으로 일괄적으로 적용되는 특징이 있다. <br>

반대로 , 복사본을 수정하면 원본도 수정이 될까?<br>
거기까진 생각을 안 해봤다. <br>
왜 자꾸만 call by reference가 생각이 나는지<br>
그 반대의 경우도 되는지 해봐야 겠다.<br>

---
<h2>벾을 만들자!!</h2><br>
Floor 게임 오브젝트 네 군데 모서리에 배치할 벽을 프리팹으로 만들어 배치 해 보자!!<br>

<div class="blueFont">
  GameObject -> 3D Object -> Cube 생성!! <br>
  Cube의 이름 : Wall <br>
  Transform 속성 :<br>
  Position : 0,3,0 <br>
  Rotation : 0,0,0 <br>
  Scale    : 50,6,1 <br>
</div><br>
