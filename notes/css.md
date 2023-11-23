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
## >(자식 결합자)와 ' '(자손결합자)
+ 클래스의 이름이 겹칠 때 구분 짓기 위해 사용
+ 부모 클래스 > 자식 클래스 .parent > .son
+ 부모 클래스 ' ' 자손 클래스 ex) .parent .son







## Modal 창 만드는 방법
+ div 태그를 하나 만들어 display: absolute, top: 0, left: 0, width: 100%, height: 100%로 
+ 하여 배경을 만들어준다.
