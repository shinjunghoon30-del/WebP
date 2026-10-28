# 10월 28일 수업내용

## 1.HTML 페이지와 자바스크립트 객체
3가지 유형의 객체를 제공받아 활용 가능

BOM (Browser Object Model) 객체: 브라우저의 창이나 탐색을 관리하는 객체
코어 객체: 자바스크립트 내장 객체
HTML DOM (Document Object Model) 객체: 웹 페이지의 HTML 태그를 제어하기 위한 객체

## 2.HTML DOM (Document Object Model)
웹 페이지에 작성된 HTML 태그당 하나의 DOM 객체(노드/엘리먼트)가 생성되는 모델

DOM 트리: HTML 태그의 포함 관계(부모-자식 관계)에 따라 노드들이 트리 구조를 형성

DOM 트리의 특징
트리의 루트(최상위)는 항상 document 객체
브라우저는 HTML 태그를 읽어 DOM 트리를 생성하고 화면에 출력하며, DOM 객체가 변경되면 즉시 화면의 태그 출력 모양을 갱신

## 3.DOM 객체의 구성 요소
- 프로퍼티 (Property): HTML 태그의 속성 반영 (예: id, tagName, innerHTML, style 등
- 메소드 (Method): HTML 태그를 제어하기 위한 멤버 함수 (예: click(), focus(), setAttribute())
- 컬렉션 (Collection): 자식 DOM 객체들의 주소를 가진 배열 형태의 집합 정보 (예: children)
- 이벤트 리스너 (Event Listener): 태그에 작성된 이벤트 반응 처리 (예: onclick, onkeydown, onload)
- CSS3 스타일: 스타일 시트 정보 반영 (style 프로퍼티를 통해 동적 제어 가능)

## 4.DOM 객체 다루기
### DOM 객체 검색
document.getElementById("id명"): 특정 ID를 가진 하나의 DOM 객체 리턴
document.getElementsByTagName("태그명"): 태그 이름이 같은 모든 DOM 객체를 컬렉션으로 리턴
document.getElementsByClassName("클래스명"): 클래스 속성이 같은 모든 DOM 객체를 컬렉션으로 리턴

CSS3 스타일 동적 변경: 자바스크립트를 통해 스타일을 실시간으로 수정 가
innerHTML 프로퍼티: 시작 태그와 종료 태그 사이의 HTML 콘텐츠를 읽거나 수정
this 키워드: 이벤트 등이 발생했을 때 자기 자신(해당 DOM 객체)을 가리키는 자바스크립트 키워드

## 5.document 객체
HTML 문서 전체를 대변하는 DOM 트리의 최상위 객체

주요 프로퍼티: location, URL, title, head, body, domain, lastModified, readyState, activeElement, documentElement 등

주요 메소드: document.write() / document.writeln(): document에 HTML 콘텐츠를 동적으로 추가

## 6.문서의 동적 구성 (생성, 삽입, 삭제)
자바스크립트를 이용해 웹 페이지 구조를 동적으로 조작 가능

DOM 객체 동적 생성: let newObj = document.createElement("태그이름");

DOM 트리에 삽입: 부모.appendChild(DOM객체); (마지막 자식으로 추가), 부모.insertBefore(DOM객체, 기준자식);

DOM 객체 삭제: 부모.removeChild(떼어내고자하는자식객체);
