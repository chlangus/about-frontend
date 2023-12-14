## Modern JavaScript 
- 현시점에 사용하기 적합한 범위 내에서 최신 버전의 표준을 준수하는 자바스크립트
- `ECMAScript` : 프로그래밍 언어의 표준이며 JavaScript가 갖추어야 할 내용을 정리해둔 설명서
- `JavaScript` : 프로그래밍 언어이며, ECMAScript를 준수해서 만들어낸 결과물
<br>

## 데이터 타입
기존 데이터 타입 + 
- `Symbol` : 기본형 데이터 타입으로 유일한 값을 만들 때 사용
  > `const user = Symbol('This is user');` : 다른 어떤것과 비교해도 false값
- `BigInt` : 기본형 데이터 타입으로 엄청 큰 수를 만들 때 사용
<br>

## typeof
- typeof(null) : object를 return
- typeof(function) : function을 return
<br>

## boolean
- false값 : false, null, undefined, NaN, 0, ''
- true값: true, [], {}, ...
<br>

## AND와 OR 연산자, null 병합 연산자
- `||` : 왼쪽이 true라면 왼쪽값 반환, 왼쪽이 false라면 오른쪽 값 반환
- `&&` : 왼쪽이 false라면 왼쪽값 반환, 왼쪽이 true라면 오른쪽 값 반환
- OR 연산자보다 AND 연산자가 더 우선순위가 높음 
- `??` : null 병합 연산자는 왼쪽이 null이나 undefined가 아니라면 왼쪽값 반환, null 또는 undefined라면 오른쪽 값 반환

## 함수 만드는 방법
- `function name() {}` : 함수 선언식, 호이스팅 
- `let name = function () {}` : 함수 표현식
- `(function () {}` : 즉시 실행 함수, 이름을 지어주더라도 외부에서 재사용 불가능, 초기화 기능에 많이 사용 
  
