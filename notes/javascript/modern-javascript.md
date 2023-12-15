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
<br>

## 함수의 형태 
- `function name() {}` : 함수 선언식, 호이스팅 
- `let name = function () {}` : 함수 표현식, 함수를 값으로 취급  
- `(function () {})()` : 즉시 실행 함수, 이름을 지어주더라도 외부에서 재사용 불가능, 초기화 기능에 많이 사용 
- `function name() { return function (){} }` : 함수를 반환하는 함수, name()()을 사용해 함수가 반환하는 함수를 호출 가능
- 다른 함수의 인자 또는 변수 등으로 사용되는 함수를 일급함수라 칭함
<br>

## 함수의 paremeter
- 파라미터에 기본값을 설정해주면, 이 함수를 호출할때 아규먼트가 없을경우 기본값이 전달 
- 함수의 아규먼트들은 `arguments` 변수에 저장되어 있음 
- arguments는 유사 배열로 사용 가능
- `...name` : rest Paremeter로 앞의 parameter가 아규먼트들로 다 차게되면 나머지 값들을 ...뒤의 변수에 할당, 배열로 사용 가능
<br> 

## Arrow Function
- `() => {return }` : return문이 한줄이라면 return 키워드 생략하여 `number => number*2` 형식으로 사용 가능
- Arguments 객체가 없고, this가 가리키는 값이 일반 함수와 다름 
<br>

## this
- 함수를 호출한 객체를 가리키는 키워드
- Arrow Function은 선언되기 직전의 this값을 가리킴 this를 사용할때는 일반함수가 권장됨
<br>

## 문장과 표현식
- 우리가 작성하는 모든 코드는 문장과 표현식으로 구성
- `문장`은 어떤 동작이 일어나도록 작성된 최소한의 코드 덩어리를 가리킴
- `표현식`은 결과적으로 하나의 값이 되는 모든 코드
<br>

## 조건 연산자
- `1 > 2 ? value1 : value2` : ? 이전 값을 비교해 truthy 하다면 value1을 return falsy 하다면 value2를 return
<br>

## Spread 구문
- `...array` : array에 담겨있는 배열을 여러개의 값으로 펼쳐줌
- 새로운 배열을 만들거나 함수의 아규먼트로 사용할 수 없음
<br>

## 프로퍼티 표기
- 변수와 객체의 프로퍼티가 똑같다면 변수의 이름만 작성해도 작동
- 프로퍼티의 이름을 `[]`로 감싸준다면 표현식의 사용이 가능해짐
<br>

## 옵셔널 체이닝
- `user.cat?.name` : user.cat의 값이 undefined나 null이라면 undefined를 반환 값이 존재한다면 name의 값을 반환 
<br>

## 구조 분해 (Destructuring)
- `const rank = ['a', 'b', 'c', 'd']`
- `const [A,B,C,D] = rank` :  순서대로 앞에서부터 변수에 값이 할당이 됨, 길이가 넘치더라도 순서가 일치하는 것들만 할당 나머지를 가져오려면 `...변수`를 사용하여 rest Paremeter 사용, 변수에 default값도 사용 가능
- `[A,B] = [B,A]` : 이 구문을 사용하여 따로 변수를 사용하지 않고 swap이 가능
- 객체를 구조분해 할때는 `const { 프로퍼티1, 프로퍼티2 } = 객체` 이렇게 사용하며 객체에 있는 프로퍼티와 동일한 이름이 있다면 할당을 해주게 되며, 없는 프로퍼티라면 undefined가 할당된다.
- 객체 구조분해에서 다른이름으로 할당하고싶다면 `프로퍼티1: 바꾸고싶은프로퍼티이름` 으로 사용하면 됨 
