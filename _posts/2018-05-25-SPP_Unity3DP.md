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
<div class="redFont"> 목표 : SNG 3D 액션 게임을 만들어 보자!
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
1. 게임 개발 환경 설정  <br>
