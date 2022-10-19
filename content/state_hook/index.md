---
emoji: 🚀
title: State Hook 사용하기
date: '2022-10-19 00:00:00'
author: 김지수
tags: 리액트 react Hook
categories: react
---

# State Hook 사용하기
```
import React, { useState } from 'react';

function Example() {
  // 새로운 state 변수를 선언하고, count라 부르겠습니다.
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

### Hook과 같은 기능을 하는 클래스 예시
```
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    );
  }
}
```

### Hook과 함수 컴포넌트
React의 함수 컴포넌트는 이렇게 생겼습니다.

```const Example = (props) => {
  // 여기서 Hook을 사용할 수 있습니다!
  return <div />;
}
```
또는 이렇게 생겼습니다.

```function Example(props) {
  // 여기서 Hook을 사용할 수 있습니다!
  return <div />;
}
```
함수 컴포넌트를 "state가 없는 컴포넌트"로 알고 있었을 겁니다. 하지만 훅은 state를 함수 안에서 사용할 수 있게 해줍니다.
Hook은 클래스 안에서 동작하지 않습니다. 하지만 클래스를 작성하지 않고 사용할 수 있습니다.

## 훅이란?
React의 useState Hook을 사용해봅시다.

```
import React, { useState } from 'react';

function Example() {
  // ...
}
```
훅은 특별한 함수입니다. 예를 들어 useState는 state를 함수 컴포넌트 안에서 사용할 수 있게 해줍니다. 

## state 변수 선언하기
클래스를 사용할 때, constructor 안에서 this.state를 { count : 0 } 으로 설정함으로써 count를 0으로 초기화했습니다.
```
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }
```
함수 컴포넌트는 this를 가질 수 없기 때문에 this.state를 할당하거나 읽을 수 없습니다. 대신, useState Hook을 직접 컴포넌트에 호출합니다.
```
import React, { useState } from 'react';

function Example() {
  // 새로운 state 변수를 선언하고, 이것을 count라 부르겠습니다.
  const [count, setCount] = useState(0);
```
### useState를 호출하는 것은 무엇을 하는 걸까요? - 변수 선언
state변수를 선언할 수 있습니다. 위에 선언한 변수는 count라고 부르지만 banana처럼 아무 이름으로 지어도 됩니다. useState는 클래스 컴포넌트의 this.state가 제공하는 기능과 똑같습니다. 일반적으로 일반 변수는 함수가 끝날 때 사라지지만, state 변수는 React에 의해 사라지지 않습니다.

### 인자로 무엇을 넘겨주어야 할까요? - 초기 값
값은 state의 초기 값입니다. 함수 컴포넌트의 state는 클래스와 달리 객체일 필요는 없고, 숫자 타입과 문자 타입을 가질 수 있습니다. 위의 예시는 사용자가 버튼을 얼마나 많이 클릭했는지 알기를 원하므로 0을 해당 state의 초기 값으로 선언했습니다.(2개의 다른 변수를 저장하기를 원한다면 두 번 호출해야 합니다.)

### useState는 무엇을 반환할까요? 
state는 변수, 해당 변수를 갱신할 수 있는 함수 이 두가지 쌍을 반환합니다. 이것이 바로 const [count, setCount] = useState() 라고 쓰는 이유입니다. 

이제 useState를 이용하여 많은 것을 만들 수 있습니다.

```
import React, { useState } from 'react';

function Example() {
  // 새로운 state 변수를 선언하고, 이것을 count라 부르겠습니다.
  const [count, setCount] = useState(0);
```
count라고 부르는 state 변수를 선언하고 0으로 초기화합니다. React는 해당 변수를 리렌더링할 때 기억하고, 가장 최근에 갱신된 값을 제공합니다. count 변수의 값을 갱신하려면 setCount를 호출하면 됩니다. 

### state 가져오기
클래스 컴포넌트는 count를 보여주기 위해 this.state.count를 사용합니다.
```
 <p>You clicked {this.state.count} times</p>
```
반면 함수 컴포넌트는 count를 직접 사용할 수 있습니다.
```
  <p>You clicked {count} times</p>
```

### state 갱신하기
클래스 컴포넌트는 count를 갱신하기 위해 this.setState()를 호출합니다.
```
 <button onClick={() => this.setState({ count: this.state.count + 1 })}>
    Click me
  </button>
```
반면 함수 컴포넌트는 setCount와 count 변수를 가지고 있으므로 this를 호출하지 않아도 됩니다.
```
  <button onClick={() => setCount(count + 1)}>
    Click me
  </button>
```


# 요약
함수 내부에서 상태 관리가 어려웠던 기존 class 문법에서 useState Hook으로 관리하게 되면 복잡했던 코드가 깔끔해지고 사용성도 향상되게 됩니다.
이 useState() 함수는 파라미터로 넘기는 초기 값과 해당 변수를 갱신할 수 있는 함수 이 두가지 쌍을 반환 합니다. 그렇기에 배열에 구조 분해 형식을 차용하여 할당하게 됩니다.

핵심은 함수 컴포넌트에서 state를 사용을 가능하게 만들고 코드의 재사용성을 높이게 됩니다.



# 질문

## useState 내부 구조는?
useState 함수 내부 까보기
```
const [fruit, setFruit] = useState('banana');

  var fruitStateVariable = useState('banana'); // 두 개의 아이템이 있는 쌍을 반환
  var fruit = fruitStateVariable[0]; // 첫 번째 아이템
  var setFruit = fruitStateVariable[1]; // 두 번째 아이템
```
- useState를 포함한 hooks는 react 모듈에 선언되어있는 함수이고,
- 함수가 실행 될 때 마다 dispatcher를 선언하고 useState 메소드 실행해서 그 값을 반환한다.
- 할당부를 거슬러 올라가니 dispatcher는 전역 변수 ReactCurrentDispatcher로 부터 가져온다.

함수가 선언부 보다 상위에 있는 값에 접근하는 것 Closure 입니다.
