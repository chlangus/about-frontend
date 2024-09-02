## javascript에서 html 태그 선택하기
- `document.getElementById('아이디이름')` : id이름으로 태그 선택        <br>     
  > id값이 존재하지 않는다면 null값이 return 
- `document.getElementsByClassName('클래스이름')` : class이름으로 모든 태그 선택 <br> 
  > class값이 존재하지 않는다면 undefined값이 return   
  > 유사배열로 배열과 비슷하게 다룰 수 있음   
  > HTMLCollection이라는 이름의 유사배열이 return      
- `document.getELementsByTagName('태그이름')` : tag이름으로 모든 태그 선택
- `document.querySelector('css선택자이름')` : css선택자 이름으로 태그 선택 <br>  
  > `querySelectorAll` : css선택자에 해당하는 모든 태그 선택 가능, NodeList란 유사배열 return  
<br>

## Event
- `이벤트` : 웹 페이지에서 발생하는 대부분의 일들   
- `이벤트 핸들링` : 자바스크립트를 통해 이벤트를 다루는 일 
- `이벤트 핸들러` : 이벤트가 발생했을 때 일어나야 하는 구체적인 동작들을 표현한 코드, 이벤트 리스너라고도 함 <br>
  > `이벤트 핸들러`를 등록 하려면 DOM객체의 프로퍼티에 등록, 또는 HTML 태크에 직접 표시
<br>

## window 
- 브라우저 창을 대변하며 자바스크립트에서 최상단에 존재하는 객체로 자바스크립트 코드 어디에서나 접근 가능하기 때문에 전역객체 라고 부른다. 
- 어떤 프로퍼티나 메소드를 사용하든 결국 전역 객체 내부의 것이기 때문에 앞에 window.을 생략할 수도 있음
<br>

## DOM(Document Object Model)
- 자식노드는 자식요소노드를 포함하며 태그가 아닌 것들도 포함됨  
- DOM을 활용해 html태그를 객체처럼 다룰 수 있게 됨
- `DOM 트리` <br>
  > 계층 구조를 가짐    
  > 부모 노드와 자식 노드의 관계로 구성되어있고, 같은 위치의 노드는 형제 노드라 부름    
  > 태그 요소 노드를 표현할때는 요소 노드, 문자를 표현할때는 텍스트 요소 노드라고 함   
  > > 텍스트 요소 노드는 요소 노드의 자식 요소 노드로 자식 요소 노드를 가질 수 없음
- 요소 노드 주요 property <br>
  > `요소 노드.innerHTML` : 요소의 안쪽에 있는 HTML을 문자열로 return, 내부의 줄 바꿈과 들여쓰기 모두 포함       
  > `요소 노드.outerHTML` : 요소를 포함한 안쪽에 있는 HTML을 문자열로 return, 내부의 줄 바꿈과 들여쓰기 모두 포함      
  > `요소 노드.textContent` : html을 제외한 text부분을 전부 return, html코드를 값으로 넣어도 text로 입력, 내부의 줄 바꿈과 들여쓰기 모두 포함   
- 요소 노드 추가하기
  1. `document.createElement` : 요소 노드 생성
  2. `요소 노드.textContent = '값'` : 요소 노드의 property 설정
  3. `부모 요소 노드.append(요소 노드)` : 부모 요소 노드에 추가할 요소 노드를 추가, 여러개의 요소 노드 추가 가능 
     > `prepend` : 부모 요소 노드의 첫번째 자식 노드로 추가   
     > `append` : 마지막 자식 노드로 추가   
     > `before` : 부모 요소 노드의 앞에 추가   
     > `after` :  부모 요소 노드의 뒤에 추가
- `요소 노드.remove()` : 요소 노드를 삭제
<br>
  
## HTML 속성
- `요소 노드.getAttribute('속성')` : 속성에 접근
- `요소 노드.setAttribute('속성','값')` : 속성값을 추가 및 수정
- `요소 노드.removeAttribute('속성')` : 속성을 삭제
> 대문자를 섞어 사용해도 소문자로 인식 
- `요소 노드.style.textDecoration = '속성값'` : javascript에서 스타일을 다룰때는 '-' 대신 camel case를 사용해서 스타일에 접근
- `요소 노드.classList.add('클래스이름')` : 클래스 이름을 추가
- `요소 노드.classList.remove('클래스이름')` : 클래스 이름을 삭제
- `요소 노드.classList.toggle('클래스이름')` : 클래스 이름을 있으면 삭제 없으면 추가
<br>

### data-로 시작하는 속성은 모두 dataset이라는 프로퍼티에 저장된다. 만약 data-status라는 속성이 있다면, element.dataset.status로 접근이 가능하다. 
<br>

## 이벤트 핸들링
- `요소 노드.addEventListener('이벤트', 이벤트 핸들러)` : 요소에 이벤트와 이벤트가 일어나면 행해질 이벤트 핸들러를 추가
- `요소 노드.removeEventListener('이벤트', 이벤트 핸들러)` : 요소에 등록된 이벤트의 이벤트 핸들러를 삭제
- 이벤트 객체의 공통 프로퍼티
  - `type` : 이벤트 이름
  - `target` : 이벤트가 발생한 요소
  - `currentTarget` : 이벤트 핸들러가 등록된 요소
  - `timeStamp` : 이벤트 발생 시각(페이지가 로드된 이후부터 경과한 밀리초)
  - `bubbles` : 버블링 단계인지를 판단하는 값
### 마우스 이벤트
- `mousedown` : 마우스 버튼을 누르는 순간
- `mouseup` : 마우스 버튼을 눌렀다 떼는 순간
- `click` : 왼쪽 버튼을 클릭한 순간
- `dbclick` : 왼쪽 버튼을 빠르게 두 번 클릭한 순간
- `contextmenu` : 오른쪽 버튼을 클릭한 순간
- `mousemove` : 마우스를 움직이는 순간
- `mouseover` : 마우스 포인터가 요소 위로 올라온 순간
- `mouseout` : 마우스 포인터가 요소에서 벗어나는 순간
- `mouseenter` : 마우스 포인터가 요소 위로 올라온 순간 (버블링이 일어나지 않음)
- `mouseleave` : 마우스 포인터가 요소에서 벗어나는 순간 (버블링이 일어나지 않음)
- 프로퍼티
  - `button` : 누른 마우스의 버튼 (0: 왼쪽, 1: 가운데(휠), 2: 오른쪽)
  - `clientX, clientY` : 마우스 커서의 브라우저 표시 영역에서의 위치
  - `pageX, pageY` :	마우스 커서의 문서 영역에서의 위치
  - `offsetX, offsetY` :	마우스 커서의 이벤트 발생한 요소에서의 위치
  - `screenX, screenY` :	마우스 커서의 모니터 화면 영역에서의 위치
  - `altKey` :	이벤트가 발생할 때 alt키를 눌렀는지
  - `ctrlKey` :	이벤트가 발생할 때 ctrl키를 눌렀는지
  - `shiftKey` :	이벤트가 발생할 때 shift키를 눌렀는지
  - `metaKey` :	이벤트가 발생할 때 meta키를 눌렀는지 (window는 window키, mac은 cmd키)
### 키보드 이벤트
- `keydown` : 키보드의 버튼을 누르는 순간
- `keypress` : 키보드의 버튼을 누르는 순간
- `keyup` : 키보드의 버튼을 눌렀다 떼는 순간
- 프로퍼티
  - `key` : 누른 키가 가지고 있는 값
  - `code` : 누른 키의 물리적인 위치
  - `altKey` : 이벤트가 발생할 때 alt키를 눌렀는지
  - `ctrlKey` : 이벤트가 발생할 때 ctrl키를 눌렀는지
  - `shiftKey` : 이벤트가 발생할 때 shift키를 눌렀는지
  - `metaKey` : 이벤트가 발생할 때 meta키를 눌렀는지 (window는 window키, mac은 cmd키)
### 포커스 이벤트
- `focusin` : 요소에 포커스가 되는 순간
- `focusout` : 요소로부터 포커스가 빠져나가는 순간
- `focus` : 요소에 포커스가 되는 순간(버블링이 일어나지 않음)
- `blur` : 요소로부터 포커스가 빠져나가는 순간(버블링이 일어나지 않음)
### 입력 이벤트
- `change` : 입력된 값이 바뀌는 순간
- `input` : 값이 입력되는 순간
- `select` : 입력 약식의 하나가 선택되는 순간
- `submit` : 폼을 전송하는 순간
### 스크롤 이벤트
- `scroll` : 스크롤 바가 움직일 때
### 윈도우 창 이벤트
- `resize` : 윈도우 사이즈를 움직일 때 발생
<br>

## 버블링과 캡쳐링
- `버블링` : 타겟 요소의 이벤트 핸들러부터 부모 요소의 이벤트 핸들러 순서대로 이벤트가 호출되는 현상
- `캡쳐링` : 버블링과 반대로 부모 요소의 이벤트 핸들러부터 시작해 타겟 요소까지 이벤트가 전파되어 호출되는 현상
- `이벤트.stopPropagation` : 버블링과 캡쳐링을 막기 위해서 사용
<br>

## 이벤트 위임
- 부모 요소에 이벤트 처리를 하여 자식 요소를 추가해도 자식요소의 이벤트가 실행되도록 하는 것
- 자식의 이벤트를 부모에게 위임 
- 원하는 자식요소에 실행을 하기 위해 처리를 해주어야 함
<br>

## 브라우저의 기본 동작
- 브라우저에는 마우스 우클릭 엔터 등 기본동작이 존재
- `이벤트.preventDefault` : 브라우저의 기본동작 막기   
