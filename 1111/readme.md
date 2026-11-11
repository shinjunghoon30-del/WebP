# 11월 11일 수업 내용

## 1. 브라우저 관련 객체 개요 (BOM)
### BOM(Browser Object Model)
- 자바스크립트로 브라우저를 제어하기 위해 지원되는 객체들의 집합으로, HTML 페이지의 내용 자체와는 관계가 없
- 국제 표준이 없어 브라우저마다 객체, 프로퍼티, 메서드가 조금씩 다를 수 있다.
### 주요 BOM 객체 종류
_ window: 브라우저 윈도우 모양 제어, 새 윈도우 열기/닫기
- navigator: 브라우저에 대한 다양한 정보 제공
- history: 브라우저 윈도우에 로드한 URL 히스토리 관리
- location: 브라우저 윈도우에 로드된 HTML 페이지의 URL 관리
- screen: 브라우저가 실행 중인 스크린 장치에 대한 정보 제공

## 2. window 객체
열려 있는 브라우저 윈도우나 탭의 속성을 나타내며, 새 페이지 로드, <iframe> 태그 생성, 또는 자바스크립트로 윈도우를 열 때 생성
### 주요 기능 및 메서드
- 윈도우 열기 (window.open): window.open(sURL, sWindowName, sFeature) 형태로 사용하며, URL 주소, 윈도우 이름(_blank, _self, _parent, _top 등), 윈도우 크기 및 모양 속성을 지정할 수 있음
- 윈도우 닫기 (window.close): 현재 윈도우를 닫거나(window.close()), 자바스크립트로 생성한 윈도우 객체를 닫을 수 있(win.close()).
### 타이머 기능
- setTimeout() / clearTimeout(): 일정 시간(msec) 후 코드를 1회 실행 또는 해제.
- setInterval() / clearInterval(): 일정 시간(msec) 주기로 코드를 반복 실행 또는 해제.
/
- 위치 및 크기 조절: moveBy(), moveTo(), resizeBy(), resizeTo()를 통해 창의 위치와 크기를 동적으로 변경할 수 있음
- 웹 페이지 스크롤: scrollBy(x, y)는 상대적 거리만큼, scrollTo(x, y)는 지정된 좌표 위치로 스크롤
- 프린트 및 이벤트: window.print()로 인쇄 다이얼로그를 호출하며, 인쇄 전후로 onbeforeprint, onafterprint 이벤트를 활용해 특정 요소(예: 회사 로고)를 제어할 수 있음
