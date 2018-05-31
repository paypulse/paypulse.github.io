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
