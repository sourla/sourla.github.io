---
title: INTELLIJ 단축키

date: 2022-01-26 23:11:00 +0900

categories: [intellij]

tags: [intellij]
---

### Windows  Intellij 필요할 것 같은 단축키 정리


+ ALT <-,-> : 파일 왼쪽 오른쪽 이동
+ ctrl Z : undo
+ ctrl shift Z : redo
+ ctrl shift I : 코드 구현부 즉시 보기
+ ctrl W  :포커스 범위 한 단계씩 늘리기
+ ctrl ctrl  ↓ : 멀티 포커스
+ F2  : 오류라인 자동 포커스
+ ctrl P  : 파라미터값 보기
+ ctrl Q : DOC 즉시보기
+ ctrl shfit \ (역슬래시) : URL 검색 / URL mapper

---

### 정규표현식으로도 단어 검색이 가능하나 설정이 필요

+ ctrl F : 현재 파일에서 찾기
+ ctrl F : 현재 파일에서 찾기
+ ctrl shift R : 전체 파일에서 교체
+ ctrl shift R : 전체 파일에서 교체

---

+ ctrl D : 한줄 복사
+ ctrl Y : 한줄 삭제
+ ctrl shift ↑↓ : 줄 위아래로 이동
+ ctrl shift N : 파일검색
+ ctrl shift alt N : method 검색
+ ctrl shift A : 액션 검색
+ ctrl E : 최근 열었던 파일 목록 보기
+ ctrl shift E : 최근 수정한 파일 목록 보기
+ ctrl space : 자동완성 **들어갈 수 있는 모든걸 보여줌**
+ ctrl shift space : 스마트 자동완성 **필터링된 기능만 보여줌**
+ ctrl Space * 2 : 스태틱 메소드 자동완성 , asserthat 같은 메소드에 쓴다는데 추후 실습해보기
+ ctrl I : override 메소드 자동완성
+ alt enter : 들어갈 수 있는 제안서를 받기

---

* ctrl J : live template 목록 보여주기

---


### 리팩토링 extract(추출) 하는 단축키


* ctrl alt V : 변수 추출하기
* ctrl alt P : 파라미터 추출
* ctrl alt M : 메소드 추출
* F6 : 이너클래스 추출 클래스 구현한 내용을 밖으로 뺄 때 사용

### 리팩토링 기타


* shift F6  : 변수명 일괄 변경
* ctrl shift F6 : 타입 일괄 변경
* inport 자동 정렬 : optimize import on 설정을 키면 됨
* ctrl alt L : 코드 자동 정렬


### Debug

* F8 : Step Over (현재 브레이크에서 다음 한줄로 이동)
* F7 : Step info 현재 브레이크의 다음 메소드 이동
* shift F8 : Step Out (현재 메소드의 밖으로 이동)
* Alt F8 : Evaluate Expression (브레이크된 상태에서 코드 사용하기 **python 인터프리터랑 비슷한 듯**)


### Git 기본기능 사용하기

* ALT 9 : git view 보는 법
* local changes 탭에서는 로컬에서 현재 변경된 내용을 알 수 있음
* log 탭은 commit 된 로그를 볼 수 있음
* ALt `(백틱) : VSC(버전 소스 컨트롤) 명령창 git option popup 띄울 수 있음
* ALt `(백틱) -> 4 : git history 보는법
* ALt `(백틱) -> 7 : branch 따는법
* ctrl k : 커밋
* ctrl shift k  : push
* ctrl shift a -> git pull : 액션에서 pull 찾아서 땡기기

### github 연동

* ctrl shift a -> share project github : github에 new repository 생성


###  추가로 단축키
* ctrl + alt + v  : 변수 바로 뽑기
* ctrl + shift + enter : 자동완성 if, try등
* 클래스명 생각 안날때,	**대문자 키워드만 챡챡챡** 쓰면 자동완성에 뜸 이걸 **calmelHumps**라고함
  * SmsPreregistServiceImpl 이걸 찾고 싶을때는 SPS라고 치고 찾으면 나옴 예제
* alt 위아래 메소드 위치 변경 java method name에 커서 놓고 alt 위아래 위치 변경할 수 있음 (함수 째로 움직임 순서 변경 쉬움)
* alt 위아래 라인 위치 변경도
* ctrl p 메소드 파라미터 보기 (수정한 단축키)
* 내꺼 단축키 등록  alt enter(ctrl 1 은 다른걸로 쓰는중)

* ctrl - 블럭 접기
* ctrl + 블럭 펴기
* alt 왼쪽 뒤로가기
* ctrl + e 최근 파일 // datagrip 과 동일
* ctrl + shift +  e 최근 파일 중 수정된 부분 // datagrip은 새로고침함
* alt shift ], [ 화면 나누기
* ctrl alt shift ], [ 화면 커서 이동 탭 쉬프터
* ctrl + alt + v  : 변수 바로 뽑기
* ctrl + shift + enter : 자동완성 if, try등
