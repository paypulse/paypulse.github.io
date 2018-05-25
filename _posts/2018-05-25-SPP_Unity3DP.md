---
layout: post
title:  "Small Project : Unity chapter 01"
date:   2018-05-25 10:59:21 +0700
categories: SPP
---
<h1> Small project : Unity3D로 게임 만들자 1탄. </h1> <br>

---
`[참고 책]` <br>
{% for post in site.posts limit:1 %}
<img src="https://paypulse.github.io/assets/images/unityBook.png" width="444" height="550"/>  
{% endfor %}
<br>

자.. 그럼 이제 시작 해 볼까?

---
<div class="redFont"> 목표 : SNG 3D 액션 게임을 만들어서 App Store에 런칭 하기!
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
</div>를 프로젝트안에 Import 시켜 준다. <br>
