# 2차 전체회의 (2023.03.19)

- 참석자 : 신혜, 윤원, 지수, 상윤, 주현, 충현

---

## 1. 메뉴바팀 진행상황

### 1) 체크박스 클릭하면 체크박스 대신 메뉴바가 나타나고 사라지는 효과 구현 (좌 → 우)

- html 영역 : check-btn에 for 을 줘서 클릭 영역(?) 지정

- css 영역
    - navbar의 z-index를 높게 줘서 리스트를 덮어버림
    - check-btn에 display-none을 줘서 처음에는 안보이게 함 (체크박스의 기능만 사용)
    - menubars에 translateX(-250px) 줘서 디스플레이 영역 밖에 존재하도록 함


### 2) 추가적으로 구현하고 싶었던 것
 
- hover했을때 submenu가 아래로 내려오는 것 (상 → 하)

    - 그러나 hover하면 나머지 메뉴가 안내려가기 때문에 submenu가 가려짐
    - 일일히 메뉴의 길이 지정해주면 submenu에 hover효과 줄 때마다 계속 길이 수정해줘야하기 때문에 좋은 방법이 아닌 것 같음

- 다크모드 효과를 하려고 했는데, 구조를 한 번 뒤집어 엎게 되면서 못 구현함
    
### 3) 기타 - 색 조합은 https://mycolor.space/ 에서 하기로 했음

### 4) 진행상황 공유 후 나온 의견들
```
1. transition-duration이 어떤 건가요? 
  → 화면 이동을 하기 위한 효과입니다.

2. transition-duration에서 1초동안 펼쳐지는 게 왜 가로가 아니라 세로인가요?
 → width 말고 height를 주었기 때문입니다.

3. 거의 대부분을 자바스크립트 말고 css로 했는데 그렇게 선택한 이유가 있나요? 
 → 가장 쉬워서입니다.

4. 차라리 쿠팡처럼 서브메뉴가 아래 말고 옆으로 하는게 어떨까요? 어차피 자바를 써야 하긴 하겠지만,구현이 쉽지 않을까요?
 → 하지만 우리가 만든게 더 까리하다는 다른팀 의견

5. 호버 말고, 클릭을 하면? 
 → 그래도 js로 넘어가지 않을까요?

6. 부트스트랩 아코디언 코드를 뜯어봐도 되지 않을까요? css 아코디언 검색해봐도 되지 않을까요?
 → https://gahyun-web-diary.tistory.com/159 아코디언 관련 참고할만한 블로그 (js 코드는 간단함. 이벤트가 발생하면 이렇게 된다! 만 써 있음)

7. menubars에 translateX 줄 때 "borderbox" 도 참고해서 적용해보라는 의견!
```
---

## 2. 케루젤팀 진행상황

### 1) 이름을 지어줄때 최대한 디테일하고, 상세하고, 세분화 시키려고 노력을 함

### 2) 구현 부분

- 사진별 인덱스를 설정함

    - 첫번째 사진은 인덱스 1, 두번쨰 사진은 인덱스 2... 이렇게 처음부터 인덱스를 정해 놓고, 사진 위치를 인덱스로 빼 준다음 적용시키는게 편하다고 생각해서 인덱스를 따로 빼줌

    - js "click"는 이벤트가 발생 했을때 인덱스 1 증가한다 → 사진 옆으로 넘어간다로 설정

    - 사이트에서는 사진이 한장 씩 넘어가는 것 처럼 보이는데, 실제로는 사진 모음이 왼쪽으로 이동 하는 것 (overflow에 hidden을 줘서 마치 다음장으로 넘어가는 것처럼 보이게 해줌)

    - 이 부분을 transition으로 구현을 해줌 (메뉴바팀의 사이드바처럼!)

    - 블로그 참조 결과 무한순회 하려면, 실제로 무한순회하는 게 아니라 마치 무한 순회하는것 처럼 보이게 해야 하는데, 순간이동 효과를 써야 함

    - 핵심은 특정 부분에 도달을 하면 잠깐 트렌지션을 0초로 만들고, 해당 사진으로 순간이동을 하는 것 (이 인덱스 순간이동 효과가 진~~~짜 어려웠음)

---
## 3. 논의 안건

### 0) 프로젝트의 목적과 유의점
- 목적1 : 무조건 즐겁게
- 목적2 : 성장
- 독성말투 추방!

### 1) 앞으로의 일정
- 케루젤팀과 메뉴바팀 모두 완벽하게 하는 것 보다 완성이 목적
- 이번주에 팀별로 좀 더 디테일하게 구현하기(3월4주)
- 다음주에 합치는 작업을 하기(3월 5주)


```
이번주 팀 별 목표
 - 메뉴바팀 : hover의 accordian 구상 완료, darkmode
 - 캐루젤팀 : 무한순회
```
 
### 2) 개발기록 작성하는 것을 어떻게 관리 할 것인가?


- 케루젤팀을 예시로 들자면, README에 큰 단위를 10분을 작성 (서기를 떠나서)
- 그 밑에 서기가 작성한 파일을 링크로 참조함
- 즉, README는 하나이고 서기는 매일 생성!
- 앞으로 개발관련 기록 (README와 서기내용)을 어떻게 관리하는 것이 좋을까?

```
앞으로 기록 내용이 길어질 것이고, 그러면 스압이 생기니까 리드미를 위한 폴더를 따로 만들어서 폴더 안에서 리드미들을 관리하는게 어떨까?

→ 디벨롭 일지 폴더를 만들어서, 그 폴더를 날짜별로 정리하고, 그날뭐했는지 적기로 함

→ 또, 매일 리드미파일을 상세하게 작성 후 링크 걸 때 그날 한 중심적인 핵심 내용을 적어 놓기가 좋을 것 같다!

 <회의에서 합의된 기록 작성 예시>

  [230319 : 페이지 구현]() : 추가적인 내용

 - readme에 최근 거  추가.md 기록모음  로 일단 작성 해보고, 문제점 있으면 수정하기!
```

 ### 3) 커밋메세지 남길때
 - Fix Add 
 - Fix carousel/carousel 전반적으로 바뀌면 : readme, html, 폴더/ 서기가작성한.md
 - Update carousel/readme.md 불가피하게 하나만 바뀐다
 - Add : navbar/ carousel
 - Update : 수정하는 과정
 - Fix : 확실한 수정

 - 매일 커밋 메시지 남기기 때문에 파일은 매일 생성할 필요는 없음 

### 4) 조 분담법
 - 한 팀이 먼저 끝나면, 다른 팀 끝날때까지 확실하게 기다려주기 
 - 기다리는 팀은 아이디어 추가, 디자인 추가 등등 하면서 기다리기
 - 모든 조의 목표달성이 끝났을 때에야 비로소 조를 바꾼다!
 - 새로 합류한 지수님은 메뉴바팀으로 결정! >_<