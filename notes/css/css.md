## CSS
+ Cascading Style Sheet
+ 개발자도구에서 위에있는것이 아래것을 덮어 씀
+ 이름이 같다면 나중에 쓰인 것이 우선
+ 선택자 명시도에 따라 우선순위 다름
+ 명시도는 아이디 개수, 클래스 개수, 요소 개수를 순서대로 숫자를 나열해서 점수를 매김
## box-sizing: border-box
+ 크기의 값이 content, 패딩, 마진값의 합이 되게 해줌

## 마진 상쇄
+ 인접해있는 요소들끼리의 마진은 상쇄될 수 있음

## RGBA
+ RGB 표기에다가 불투명도(Alpha)를 추가한 것
+ 불투명도는 0 ~ 1 사이의 소수점 숫자

## background-image: linear-gradient(rgba(), rgba())
+ 앞의 색에서 뒤의 색으로 기본설정인 위에서 아래로 색이 바뀌는것으로 설정
## em과 rem
+ 1em은 부모 태그의 font-size
+ 1rem은 최상위 태그(html 태그)의 font-size   

## inline
+ 크기가 존재하지 않음
+ 인라인 속성이면서 크기를 설정하고 싶다면 display: inline-block 속성으로 설정

## %
+ %의 기준은 예를 들면 left: 50% 일때 왼쪽 면이 화면의 중간에 위치 

## float 속성
+ 기존 구조에서 벗어나 원하는 곳에 배치 가능

## letter-spacing, word-spacing
+ 글자 사이의 간격 조정할때는 letter-spacing: px; 로 사용
+ 단어 사이의 간격 조정 시 word-spacing 사용

## z-index
+ 숫자가 클 수록 위에 위치
+ 쌓임맥락으로 인해 부모의 z-index가 1이고 자식의 z-index가 3이어도 밑에 있는 태그의 z-index가 2라면 부모와 자식 둘 다 우선순위가 낮음 즉 부모의 z-index를 따라감

## position
+ static: 기본값, 일반적인 글의 흐름을 따름
+ relative: static의 위치를 기준으로 움직임, 원래 위치는 비어져 있음
+ absolute: 포지셔닝된 가장 가까운 조상요소를 기준으로 움직임, 원래 위치에 자리를 차지하지 않음 inset:0은 top, right, bottom, left 모두 0으로 설정
+ fixed: 스크롤해도 지정한 위치에 고정, 원래 위치의 자리를 차지하지 않음, 크기 지정해줘야 함
+ sticky: 원래 자리에 있다가 지정한 위치에 닿으면 fixed처럼 고정됨, 부모요소가 사라지면 사라짐, block요소

## >(자식 결합자)와 ' '(자손결합자)
+ 클래스의 이름이 겹칠 때 구분 짓기 위해 사용
+ 부모 클래스 > 자식 클래스 .parent > .son
+ 부모 클래스 ' ' 자손 클래스 ex) .parent .son

## flex-box
+ display: flex;
+ 기본값: row 즉 가로로 겹겹이 쌓임
+ flex-direction: row, row-reverse, column, column-reverse
+ justify-content: 기본축의 간격 및 위치 설정
+ align-items: 교차축의 간격 및 위치 설장
+ flex-wrap: wrap; 넘치는 요소를 다음줄에 보여줌
+ flex-grow: 1, flex-shrink: 0

## grid 
+  grid-template-columns: 100px 300px 100px; : 각 컬럼의 너비
+  grid-template-rows: 200px 200px 100px : 각 row의 높이
+  repeat(3, minmax(200px, 300px)) 3번 200px에서 300px까지 늘어남
+  grid-auto-rows/colums : 자동으로 행이나 열의 크기 지정 
