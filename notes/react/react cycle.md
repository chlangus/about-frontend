## 리액트 생명주기
![image](https://github.com/chlangus/frontend-note/assets/139041897/cb25a710-9a67-4aeb-89e7-2bacdc9a013a)
<br>
위 그림에 나온것처럼   
리액트의 생명주기는 마운트, 업데이트, 언마운트 이 세 단계로 나누어져있습니다.   
- 마운트 
  > 먼저 마운트 될때 constructor, 즉 생성자 메서드가 실행됩니다.    
  > 두번째로 getDerivedStateFromProps함수는 props로 받아온 것을 state에 넣어주고 싶을 때 사용합니다.
  > 그리고 rendering을 하게 됩니다.   
  > 렌더링을 마치고 나면 componentDidMount 메서드가 호출되어 화면에 컴포넌트가 나타나게 됩니다.
<br>

- 업데이트
  > props나 state가 바뀌었을 때 getDerivedStateFromProps 메서드가 호출됩니다.
  > shouldComponentUpdate 메서드는 컴포넌트가 리렌더링 할지 말지 결정하는 메서드 입니다.
  > rendering을 하게 됩니다.
  > 컴포넌트에 변화가 일어나기 직전의 DOM 상태를 가져와 특정 값을 반환하면 그 다음 발생하게 되는 componentDidUpdate 함수에서 받아와서 사용 할 수 있습니다.
  > componentDidUpdate는 리렌더링이 마치고, 화면에 우리가 원하는 변화가 모두 반영되고 난 뒤 호출되는 메서드입니다. 3번째 파라미터로 getSnapshotBeforeUpdate에서 반환한 값을 조회할 수 있습니다.
<br>

- 언마운트
  > componentWillUnmount는 컴포넌트가 화면에서 사라지기 직전에 호출됩니다.
  > 주로 DOM에 직접 등록했었던 이벤트를 제거합니다.
