# 11월 4일 수업 내용

## 1. 이벤트 개요 및 리스너 작성 방법
### 이벤트(Event)
- 사용자의 입력 행위(마우스 클릭, 키보드 입력 등)나 문서·브라우저의 상태 변화(로딩 완료, 타이머 타임아웃 등)를 자바스크립트 코드에 알리는 통지(Notification)
- 이벤트 종류는 HTML5 기준 70여 가지가 존재하며, 리스너 이름은 이벤트 이름 앞에 on을 붙여 사용 (예: onmousedown, onkeydown)

### 이벤트 리스너 작성 방법
- HTML 태그 내 작성: 태그의 이벤트 리스너 속성에 코드를 직접 작성 (예: onmouseover="...")
- DOM 객체의 이벤트 리스너 프로퍼티 이용: 자바스크립트에서 DOM 객체를 가져와 프로퍼티에 함수를 등록 (예: p.onmouseover = over;)
- addEventListener() 메소드 이용: 표준적인 등록 방법으로, 캡처와 버블 단계를 세밀하게 제어
- 익명 함수 이용: 이름 없는 함수를 활용하여 코드가 짧거나 한 곳에서만 쓰이는 경우 유용하게 작성

## 2. 이벤트 객체와 디폴트 행동
### 이벤트 객체(Event Object)
- 발생한 이벤트에 관련된 다양한 정보(마우스 좌표, 키 코드 등)를 담고 있는 객체로, 이벤트 리스너의 첫 번째 매개변수(e)로 전달
- 공요 멤버: type(이벤트 종류), target(이벤트를 발생시킨 객체), currentTarget(현재 리스너를 실행 중인 객체), preventDefault()(디폴트 행동 취소 메소드) 등

### 이벤트의 디폴트 행동 취소
- 특정 이벤트가 가진 기본 동작(예: <a> 링크 클릭 시 페이지 이동, submit 버튼 클릭 시 폼 전송)을 막는 방법
- 이벤트 리스너에서 false를 리턴하거나 이벤트 객체의 event.preventDefault() 메소드를 호출하여 취소

## 3. 이벤트 흐름 (Event Flow)
### 이벤트 흐름의 개념
- 이벤트가 발생하면 window 객체에서 출발하여 DOM 트리를 따라 타겟 객체에 도달(캡처 단계)한 뒤, 다시 반대 방향으로 흘러 window 객체에 도달하고 소멸하는 과정
### 단계별 특징
- 캡처 단계 (Capturing Phase): window에서 중간 DOM 객체를 거쳐 타겟 객체로 전달되는 과정
- 버블 단계 (Bubbling Phase): 타겟에서 중간 DOM 객체를 거쳐 window 객체로 전달되는 과정
### 리스너 등록 및 제어
- addEventListener(eventName, listener, useCapture)에서 3번째 인자가 true이면 캡처 리스너, false(디폴트)이면 버블 리스너로 등록
- 이벤트 객체의 event.stopPropagation()을 호출하면 이벤트 흐름을 중단

## 4. 마우스 및 키 핸들링
### 마우스 관련 이벤트 리스너
- onmousedown / onmouseup: 마우스 버튼을 누르거나 뗄 때
- onmouseover / onmouseout: 마우스가 태그 위로 올라오거나 내려갈 때 (자식 영역 포함)
- onwheel: 마우스 휠을 구르는 동안 호출 (wheelDelta 프로퍼티로 방향 확인 가능)
- onmousemove: 마우스가 움직일 때 발생하며 좌표 정보(clientX, clientY, offsetX, offsetY 등) 제공
- oncontextmenu: 마우스 오른쪽 클릭 시 컨텍스트 메뉴 출력을 제어 (false 리턴 시 메뉴 금지)

### 키 관련 이벤트 리스너
- onkeydown: 키가 눌려지는 순간 모든 키에 대해 호출
- onkeypress: 문자 키와 <Enter>, <Space>, <Esc> 키에 대해 추가 호출
- onkeyup: 눌러진 키가 떼어지는 순간 호출
- 이벤트 객체의 e.key(키 문자열) 및 e.code(키 코드)를 통해 입력된 키를 판별

## 5. 문서 및 이미지 로딩, 폼(Form) 요소 활용
### 로딩 완료 (onload)
- HTML 문서: 웹 페이지 전체 로딩 완료 시 window.onload 또는 <body onload="...">를 통해 호출
- 이미지: 이미지 로딩 완료 시 정확한 크기(width, height)를 얻기 위해 img.onload 리스너 내부에 코드를 작성, 동적으로 이미지를 생성할 때는 new Image()를 활용

  ### 포커스 (onfocus, onblur)
  - onfocus: 포커스를 얻을 때, onblur: 포커스를 잃을 때 발생하며 유효성 검사 등에 활용
 
  ### 폼 요소 제어 (radio, checkbox, select)
  - 라디오 버튼 / 체크박스: document.getElementsByName() 등으로 요소들을 가져와 .checked 속성으로 선택 여부를 확인하고 값을 계산
  - Select 객체: <select> 콤보박스는 선택된 옵션의 인덱스(selectedIndex)나 변경 이벤트(onchange)를 통해 동적인 인터페이스를 구현
  - onsubmit / onreset: <form> 태그에 적용되어 전송 및 초기화 동작을 제어
