---
layout: post
title:  "Google Cloud Onboard"
date:   2018-06-12 10:59:21 +0700
categories: SUS
---
<h1>Google Cloud Onboard</h1><br>

---
<h2>Keynote</h2><br>
Google 자격증에 대해서 찾아 보고 커리어에 도움이 되기를  <br>

`Google Cloud `<br>
비용 절감만이 문제가 아닌 Business 파트너로 사용 하고 있다. <br>
기술과 최고급 제품을 기반으로 하여 단골을 포섭 하라 라는 마케팅을 실현 하고 있는 구글<br>

구글 클라우드가 집중 하는 근본 원리<br>
1. 보안 , 네트워크 , 유연한 인프라 스트럭처 <br>
Lift and Improve<br>

Google Cloud Platform 리전 <br>
지역으로 클라우드 구축이 됬다는 것을 의미 <br>

구글의 큰 특징은 구글 자체로 구축해 놓은 백본 스트럭처를 가지고 있다. <br>

`구글 네트워크 차별성 `<br>
자체 구축으로 인한 지연 시간 낮음 등 ..<br>

---
<h2>Google Cloud Platform 소개</h2><br>

이메일이나 Rock place로 문의 하기<br>

코로케이션 기법이 나오면서 대여해서 사용 하는 방법이 나왔다. <br>
VMware 같은 가상 머신 기능을 이용해, 1개의 웹호스팅 기술이 있었다면 한 서버에 여러개의 버추얼 머신을 사용할 수 있다. <br>
서버리스 - VM도 없고 Docker도 없이 오로지 Function으로만 관리 되는 기술이다. <br>
존 - 독립적인 데이터 센터라고 보면 된다. 자연 재해가 나도 어플리 케이션 배포에 문제가 없다. <br>
멀티 존과 같은 서비스를 사용 해도 충분 하다. <br>

구글에서 보안은 최우선 사항이다. <br>
google git repo? ==> 찾아 봐야 겠다.

cloud shell : 개발자용 VM , 이용하여 개발 할 수 있다.<br>

---
<h2>Google Cloud Platform 시작하기</h2><br>

구글 클라우드 플랫폼을 이용한다고 해서 보안에 철저하게 도움이 되는게 아니라, 사용자도 지켜야 한다.
ex) 깃 허브에 API 키가 노출 되는 경우 <br>
Project를 Account 라고 부르기도 하고, 구글에서는 Project라고 불리운다. <br>
Project 가 만들어짐과 동시에 Builing Account를 만들어야 한다. <br>
즉, 권한의 범위를 나뉜다. <br>
IAM : Identity Account Management <br>

구글의 모든 인증은 OAuth 2.0을 사용한다.<br>
구글의 모든 레퍼런스 + 테스팅 툴 제공 : APIs Explorer <br>
APIs Explorer의 call은 가상이 아니기때문에, Project에 직접 Call이 되어진다. <br>
Google 2.0 OAuth play ground 와 같은 곳에서 인증 받는 절차를  explorer에서 단계별로 받을 수 있다. <br>

위의 2가지 툴을 이용해 Google API를 사용한 개발이라면, 도움이 된다. <br>

Cloud Launcher<br>
구글에서 제공하는 마켓이라고 보면된다. <br>

설명들 자체가 핸즈온을 필요로 하는데... 추후 다시 정리 할때, 해볼 수 있었으면, 아마 유투브에 있겠지 <br>
많은 파트너사들이 있지만, 비용이 얼마나 드는지 너무 궁금 하다.

---
<h2>클라우드 환경에서의 가상 머신</h2><br>
VPC : 가상 사설 클라우드 네트워크<br>
VPC는 많은 인터네트워킹 기능 제공 해준다. <br>
글로벌 로드 밸런스를 이용해서 혹시나 모를 장애에 대비 할 수 있다. <br>

---
<h2>클라우드의 저장소</h2><br>
이 역시 핸즈온인데, 실습을 강사만 하고 있다. 아무리 google cloud 소개 라지만, 그래도 중간 중간 설명은 해줘야지  <br>

<br>
명령어도 gcloud로 시작한다. 신기하군 <br>
개발 환경을 사용자나 개발자 중심으로 어떻게 하면 cloud 에서 개발 환경을 설정해서 개발하기 편리 하게 할 지 <br>
gcloud compute ssh ~~~이렇게 시작 한다. 명령어가.

cloud storage <br>
object storage , block data [binary data]를 저장 한다. 모든 google cloud 사용자가 유니크한 이름을 사용해야 한다. <br>
클래스가 다르면, 서로다른 서비스로 API로 다이나믹한 클래스를 가질 수 있고, 라이프 사이클인 룰셋을 사용 할 수 있다. <br>

Cloud Bigtable는 관리형 NoSQL <br>
Bigtable이 굉장히 큰 크기의 Row를 저장 할 수 있고, 낮은 레이턴시를 제공한다. <br>
클러스터를 먼저 만들어야 한다. 샤딩되어서 기본적으로 데이터 베이스에 저장이 되는데 샤딩의 리벨런싱을 자주 해준다.<br>
시간이 지나면 리니어한 성능의 향상을 기대 할 수 있다. <br>
배포한 성능을 활용 할 수있게 된다.  <br>

Bigtable 액세스 패턴 <br>
스트리밍 데이터 : 처린한/처리할 데이터를 빅테이블이 가져 온다. <br>

Cloud SQL 의 모든 권한은 IAM에서 관리 한다.<br>
Cloud Spanner <br>
기존의 RDBMS 사용 하듯이 사용 하면 된다. <br>
Bigtable과 DataStore모두 NoSQL이다. <br>
NoSQL이라 스키마 없이 테이블을 정의 할 수 있다. <br>
BigQuery는 분석 솔루션으로 유명하다. Big Query내에 저장, NoSQL인데,

실습을 해야 하는데 인터넷이 연결이 안된다. ㅠㅠ<br>

---
<h2>클라우드의 컨테이너</h2><br>

구글에서 도커를 사용하다가 만들어진게 Kubernetes엔진이다.<br>

---
<h2>클라우드 어플리케이션</h2><br>
java, python, javascript, ios, android <br>

---
<h2>클라우드에서 개발, 배포 및 모니터링 </h2><br>
Cloud Function : 컨테이너의 작은 단위에 해당 한다. <br>
모바일 개발 업체들이 많이 사용 한다. <br>

deployment manager <br>
인프라 매니저는 코드를 관리 한다. <br>
인프라 스트럭처의 버져닝이 가능해 진다. <br>

STack driver <br>
모니터 리포팅, 로깅, 디버그 콘솔, 에러 리포팅, 웹 트레이스, Http 로드 밸런스 <br>
모니터링 결과에 따라 여러가지 노티피 케이션을 받을 수 있다. <br>
로깅 에이전트도 제공 한다. <br>
매트릭 로깅이라는 것을 제공한다. <br>

Stack driver는 별도로 생성해서 설정을 해줘야 한다. <br>

---
<h2>클라우드의 빅데이터 및 기계 학습</h2><br>
각 서비스의 이름과 키워드정도 알아야지. 구글 클라우드 Document를 많이 따라 해보자.<br>
Quickstart 같은거 많으니까 수업 이후에 참조 해보자. <br>
Data Studio : Google Analytics 상품군에 들어가 있다. <br>
job 단위로 클러스터를 생성하고 , 지우고 <br>

핸즈온에 대해 구체적으로 더 알고 싶다면, 구글 클라우드 Document를 많이 참조 하자.<br>
Cloud DataFlow는 관리형 데이터 파이프라인 제공 <br>
스트리밍 처리에 굉장히 유연 하다. <br>
Data Flow는 Job에 대한 분배를 잘 해준다. <br>

Big Query<br>
수백 테러바이트에 대해서 속도를 빠르게 처리해서 가져 올 수 있게 해준다. <br>
Data store처럼 Data set을 만들면 바로 사용 할 수 있다. <br>
map reduce 논문을 가장 이상적으로 구현한 솔루션이라고 볼 수 있다. <br>

쿼리당 비용이 발생 한다. 여기서 발생한 비용은 쿼리당 스캔한 비용이 든다. <br>

pub/sub : Push / Pull 처리가 가능하다. <br>
데이터 플로우의 실시간 데이터 전달 매개체로 사용을 많이 한다. <br>
완전 관리형 서비스이다. <br>
클라우스 Function이 Pub/sub을 많이 사용한다. 애플리 케이션간의 연결을 위해 사용 <br>

Big query의 query를 뽑아 비쥬얼라이즈 할 수 있다. <br>

Cloud 기계 학습 <br>
TensorFlow : 머신러닝을 편하게 구현하기 위한 라이브러리<br>
학습할 환경을 제공해주는 것을  Cloud ML이라고 한다. <br>
Cloud ML을 이용해 나만의 인프라를 손쉽게 구축 할 수 있다.  <br>

Cloud vision API<br>
사진에 대한 메타데이터(위치,감정상태,어딜 바라 보는지, 몇명인지등등을 수치화 해서 )를 유추해서 알려준다. <br>

Cloud Speech API<br>
실시간으로 사용 할 수 있다.  ex). 번역 <br>

Cloud Natural Language API <br>
콜 센터에서 사용자에 대한 채팅 로그에 대해 어떤 대답을 할지 머신런닝을 해서 대처 해준다. <br>

Cloud Translation API <br>
번역 API <br>
Speach API와 함께 사용 하면 , 실시간 처리가 가능해 진다.  <br>

Cloud Video Intelligence API <br>
정적인 이미지에 대한 분석이 아닌 동영상에 대한 분석을 통해 결과물을 처리해준다. <br>

오늘 수업은 진짜 빨리 진행 됬을 뿐만 아니라.무료 와이파이가 잡히지 않아. 실습은 커녕 그냥 엄청 빨리 실습 내용을 바라 볼 수 밖에 없었다.
너무 아쉽다. <br>
