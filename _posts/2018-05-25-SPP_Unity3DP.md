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
    `Position` : 0,3,0 <br>
    `Rotation` : 0,0,0 <br>
    `Scale`    : 50,6,1 <br>
</div><br>

마찬가지로 Wall에 Texture를 입히자 <br>
`Wall Material` <br>
1. 이름   : Wall <br>
2. 셰이더 : Mobile/Diffuse<br>
3. Texture: 04.Images -> Stages -> wall <br>
4. Tiling : x : 10
<div class="blueFont">
Standard가 아닌 Mobile/Diffuse를 선택한 이유는? <br>
Standard는 모바일 플랫폼에서 무겁기 때문이다.<br>
</div><br>
Wall 게임 오브젝트를 선택 하고, Mash Renderer ->  Materials -> Element 0 에 연결 <br>

---
<h2>Wall GameObject로 프리팹을 생성 하자.</h2><br>
<div class="blueFont">
  1. 03.Prefabs -> Create -> Prefab <br>
  2. Prefab 이름 : Wall <br>
  3. Hierachy view의 Wall을 Prefab에 Drag and Drop 한다.
</div><br>

---
<h2>Prefab을 복제 하자!</h2><br>

<div class="redFont">
  게임 오브젝트,프리팹,각종 리소스는 무론 Scene도 복사할 수 있다.
</div><br>
사각면이니까 벽4개 만들어야지.<br>
Duplicate 눌러도 되지만, 단축키를 이용하자,현대인 이잖아 도구를 써야지 <br>
[단축키] : <br>
맥 => Command + D <br>
윈도우 => Ctrl + D <br>
복제한 Wall Prefab들을 각 모퉁이에 배치 해준다. <br>

---
<h2>스내핑?</h2><br>
사전적 의미 : 딱 소리 내는, 딱 소리 내는, 딱 하고 부러뜨리다.<br>
Unity에서 Snapping의 의미 : 3차원 공간을 다루다 보면, 여러 오브젝트를 다루는데 빈틈이 생기기 마련인데, Unity 3D에서는 이러한 빈틈을 최대한 줄여주고자 snap 기능을 제공한다. <br>

즉, 딱 들어 맞게 해준다. 이런 의미인가 보다. ㅋ<br>

Vertex Snapping을 이용해서 쉽고 편리 하게 화면을 배치 할 수 있다. <br>

※ Vertex Snapping 방법 : 키보드 V키를 누른 상태에서 마우스 커서를 특정 정점 근처로 옮기면, Transform축의 해당 정점으로 이동한다. <br>

그런데 난 잘 모르겠다. 솔직히 항상 눈대중인가. <br>

---
<h2>Lighting</h2><br>
조명을 효율적으로 사용하느냐에 따라 게임의 분위기나 완성도가 달라질 정도로 중요한 요소이지만, 그렇다고 너무 많이 사용하게 되면, 조명 처리를 위한 렌더링 과부하가 생긴다. 그렇기 때문에 최소한 양으로 시각 효과를 내야 한다. <br>

<div class="redFont">
  유니티는 게임 속도를 저하 하지 않고, 실시간 조명효과를 낼 수 있는 Lightmapping 및 Light Probe 기능을 제공 한다.
</div><br>
전에 Lightingmapping 인가? 적용해본적 있었는데, Build 할때 조금 시간 걸렸던것 같았었는데. <br>

※유니티가 제공 하는 조명 종류 <br>
1. Directional Light <br>
  - 태양과 같은 조명, 위치는 어디에 있어도 상관 없고, 빛을 비추는 각도에 따라 그림자의 방향과 길이가 달라진다.<br>
2. Point Light <br>
  - 백열 전구와 같은 조명, Point Light가 위치한 좌표를 중점으로 주변으로 퍼져나가는 조명이기 때문에 빛이 미치는 범위 Range 속성이 있다. <br>
3. Spot Light <br>
  - 연극 무대의 독백 조명, 빛이 뻗어 나가는 각도를 조절 할 수 있는 Spot Range 속성이 있다. <br>
4. Area Light <br>
  - 사각형 형태의 조명으로 한쪽 면에서 빛을 발하는 조명으로, 라이트 맵을 베이크 해야만 확인 할 수 있다. 유니티에서 제공하는 4개의 조명중에서 Area Light만 실시간 조명이 아니며, 간접 조명으로 사용 한다. <br>

※Light 추가 방법 <br>
<div class="blueFont">
  GameObject -> Light
</div><br>

Scene이 만들어지면, 기본적으로 Directional Light는 생성되어 있다. <br>

※실시간 Light 조명 끄는 방법<br>
실시간 전역 조명을 끄고 베이크를 하는 것이 유니티 에디터의 속도를 떨어 뜨리지 않는다. ---> 그래서 전에 Build 속도가 느렸었나 보다. <br>

<div class="blueFont">
  [Window] -> [Lighting] -> [Setting]을 선택하면, Light view가 열린다. Auto Generate 옵션을 언체크 하면 실시간 라이트 매핑 처리를 하지 않는다.
</div><br>

---
<h2>하늘 표현 방식</h2><br>
아마 WebGL 하면서 도전하지 않을까 싶지만, 전에 Directx로 3D개발 할땐, 하늘과 배경을 사각 박스 안에 넣어서 그런지 이음새 처리가 만족 스럽지 않았었는데. 원형 돔 형식으로 처리를 하고 싶다고 생각만 했지. 구현해 본적은 없다. <br>

※게임에서 하늘을 표현하는 대표적인 방식<br>
1. Skybox : 카메라가 볼수 있는 하늘을 여섯방면 (left, front, back, top, bottom)의 이미지를 Cube 형태로 배치해서 표현 <br>

2. SkyDome : 돔 형태의 매쉬에 하늘의 이미지 텍스처를 입혀서 구현한다. <br>

---
<h2>6방면 스카이 박스</h2><br>
<div class="blueFont">
  1. 04.Images/Materials 폴더에 new Material 추가 <br>
  2. Material 이름 : Skybox <br>
  3. Material shader 속성 : [Skybox] -> [6 sided] 로 바꾼다. <br>
  4. 에셋 스토어에서 내려 받은 Skybox Volume2 원하는 이미지를 고른다. <br>
  5. 6 Sided -> Front, Back,Left,Right,Up, Down에 차례로 매칭 해준다.<br>
  6. Skybox 니까 Down이 없을 수도 있다.
  7. Exposure 속성은 Skybox 텍스처의 노출을 설정 하는것으로 밝기를 조절 할 수 있다.<br>
  8. Rotation 속성은 Y축을 기준으로 시계방향 [+방향]으로 회전 시킬수 있다.<br>
  9. Window -> Lighting -> Setting ---> Lighting view가 열린다.
  10. Lighting view ---> Evironment -> Skybox Material -> texture를 넣은 material을 추가 해준다.
</div><br>

나는 `DeepSpaceBlue` 으로 선택!<br>

---
<h2>프로시저럴 스카이박스</h2><br>
유니티 5부터 Skybox의 구현이 3가지 형태로 확장이 되었다. ---> 그렇군 <br>
1. 6 sided <br>
2. Procedural <br>
3. Cubemap <br>

※Procedural Skybox의 특징 : 하늘의 색상, 대기 농도, 노출(밝기), 태양의 위치와 크기 등을 설정 할 수 있다. <br>
유니티 프로젝트 생성후 보이는 스카이 박스가 프로시저럴 스카이 박스 이다.<br>

기본 값인 Default-Skybox는 여러가지 설정 값을 수정 할 수 없으므로 별도의 프로시저럴 스카이 박스 머티리얼을 만들어야 한다. <br>
<div class="blueFont">
  1. 04.Images/Materials 폴더에 new Material 추가 <br>
  2. Material 이름 : SkyboxPC <br>
  3. Material shader 속성 : [Skybox] -> [Procedural] <br>
</div><br>

게임에서 해가 뜨고 지는 시스템을 도입한 경우 태양 이미지의 위치가 태양의 고도에 따라서 위치가 같이 변경 돼야 한다. <br>
라이팅 뷰의 Sun Source 속성에 Directional Light를 드래그 해서 연결 한다. <br>

---
<h2>큐브 맵 스카이박스</h2><br>
큐브 맵은 여섯 방면 스카이박스와 마찬가지로 6장 텍스처가 필요 하며 주면 환경을 반사하는 효과에 주로 사용 한다. <br>
큐브 맵은 6sided 스카이 박스와 마찬가지로 6장의 텍스처가 필요 하며, 주변 환경을 반산하는 효과를 주로 사용 한다.<br>

----
6Side Skybox의 드로우콜 소모량 <br>
6 Side Skybox는 6개의 텍스처를 사용하므로 6드로우콜을 소모하지만 큐브맵 스카이박스와 프로시저럴 스카이박스는 1드로우콜만 소모하기 때문에 좋은 대안이 될 수 있다.<br>
또한 SkyDome 역시 1장의 텍스처를 사용 할 경우 1드로우 콜만 소모하기 때문에 드로우콜을 낮출 수 있다는 장점이 있다. 하지만, SkyDome 방식은 게임의 특성에 따라 카메라가 볼수 있는 최대 거리를 제한 해야 할때는 SkyDome 방식을 적용 하는 것은 적합 하지 않을 수 있다. <br>

---
<h2>3D 모델을 불러 오자!</h2><br>
모델을 불러 왔는데 텍스쳐가 깨졌다. 그럴땐 당황하지 말고, Import Materials에 check를 해준다.<br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/import1.png" width="383" height="553"/>  
{% endfor %}

Player 객체를 Drag and Drop 후 <br>
<div class="blueFont">
  Transform의 Position 속성을 (0,0,0)으로 설정
</div><br>

---
<h2>Component</h2><br>
유니티는 component 기반 개발 방법론을 지원 한다. <br>
<div class="blueFont">
Component 개발 방법 론이란? 독립적인 기능 단위로 component를 제작해 필요한 기능을 조립 하는 방식이다.
이런 방식의 가장 큰 장점은 컴포넌트의 재사용이 가능하여 생산성이 장점이다.
</div><br>

---
<h2>캐릭터를 controll 할 script를 작성 하자!!</h2><br>

<div class="redFont">
  PlayerCtrl 이란 스크립트를 만들자!!
</div><br>
 스크립트 명과 클래스명은 동일 해야 한다. <br>

 ---
 <h2>유니티에서 사용 되는 함수 목록</h2>
1. Awake <br>
  - 스크립트가 실행 될때 한번만 호출되는 함수다. <br>
  - 주로 게임의 상태 값 또는 변수의 초기화에 사용한다. <br>
  - Start 함수가 호출 되기 전에 맨 먼저 호출 된다. <br>
  - 스크립트가 비활성화 돼 있어도 실행 된다. <br>
  -코루틴으로 실행 불가 <br>
2. Start <br>
  - Update 함수가 호출 되기 전에 한번만 호출 된다. <br>
  - 스크립트가 활성화 돼 있어야 실행 된다. <br>
  - 다른 스크립트의 모든 Awake가 모두 다 실행된 이후에 실행된다. <br>
  - 코루틴으로 실행 가능 <br>
3. Update <br>
  - 프레임 마다 호출 되는 함수로 주로 게임의 핵심 로직을 작성한다. <br>
  - 스크립트가 활성화돼 있어야 실행 된다. <br>
4. LateUpdate <br>
  - 모든 Update 함수가 호출되고 나서 한번씩 호출 된다. <br>
  - Update 함수에서 전처리가 끝난 후 실행해야 하는 로직에 사용한다. <br>
  - 카메라 이동 로직에 주로 사용하는 함수다. <br>
  - 스크립트가 활성화 돼 있어야 실행된다. <br>
5. FixedUpdate <br>
  - 물리 엔진의 시뮬레이션 계산 주기로 기본 값은 0.02초이다. <br>
  - 발생하는 주기가 일정하다. <br>
6. OnEnable <br>
  - 게임 오브젝트 또는 스크립트가 활성화됐을때 호출 된다. <br>
  - 이벤트 연결시 사용한다. <br>
  - 코루틴 사용 불가 <br>
7. OnDisable <br>
  - 게임 오브젝트 또는 스크립트가 비활성화됐을때 호출된다. <br>
  - 이벤트 연결을 종료할때 사용한다. <br>
  - 코루틴 사용 불가 <br>
8. OnGUI <br>
  - 레거시 GUI 관련 함수를 사용할때 사용 한다.

  <div class="redFont">
    솔직히 정리 안하는 것보다는 정리 하는게 낫다. 일단은 프로젝트 하면서 자주 사용하는게 최선인것 같다.
  </div><br>

----
<h2>키보드 입력 값을 받아 오자. </h2><br>
