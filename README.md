# JSX문법

- 최상위 요소가 하나여아 한다
- 최상위 요소 리턴하는 경우, ()로 감싸야 한다.
- 자식들을 바로 랜더링 하고 싶으면, <>자식들</>를 사용한다 =>Fragment
- 자바스크리비트 표현식을 사용하려면, {표현식}를 이용
- if 문 사용 불가
  - 삼항 연산자 혹은 && 를 사용
- style을 이용해 인라인 스타일링이 가능함
- class 대신 className을 사용해 class를 적용 할 수 있음.
- 자식요소가 있으면, 꼭 닫아야하고, 자식요소가 없으면 열면서 닫아야함.
  - \<p>룰루랄라\</p>
  - \<br/>

---

# Props와 State

- Props는 컴포넌트 외부에서 컴포넌트 에게 주는 데이터
- State는 컴포넌트 내부에서 변경할 수 있는 데이터

<br/>
둘 다 변경이 발생하면, 랜더가 다시 일어날수 있음

---

## Render 함수

컴포넌트를 그리는 방법을 기술하는 함수가 랜더함수

Props와 State를 바탕으로 컴포넌트를 그림
그리고 변경되면 컴포넌트를 다시 그림.

# Event Handling

- camelCase 로만 사용할 수 있다.
  - onClick, onMouseEnter
- 이벤트에 연결된 자바스크립트 코드는 함수
  - 이벤트={함수} 와 같이 씀
- 실제 DOM 요소들에게만 사용 가능함
  - 리액트 컴포넌트에 사용하면, 그냥 props로 전달함

# Component Lifecycle

탄생 => 죽음

initialization - Mounting - Updation - Unmounting


## componetWillReceiveProps

- props를 새로지정했을 때 바로 호출됨
- 여기는 state의 변경에 반응하지 않음
  - 여기서 props의 값에 따라 state를 변경해야 한다면
    - setState를 이용해 state를 변경합니다.
    - 그러면 다음 이벤트로 각각 가는것이 아니라 한번에 변경됨

## shouldComponentUpdate

- props 만 변경되어도
- state만 변경되어도
- props & state 둘다 변경되어도
- newProps와 new State를 인자로 해서 호출
- return type이 boolean
  - true 면 render
  - false면 render가 호출 되지 않음
  - 이 함수를 구현하지 않으면, 디폴트 true

## componentWillUpdate

- 컴포넌트가 재 랜더링 되기 직전에 불림
- setState같은 것은 쓰면 안됨

## componentDidUpdate

- 컴포넌트가 재랜더링을 마치면 불림

## Component 에러 캐치
