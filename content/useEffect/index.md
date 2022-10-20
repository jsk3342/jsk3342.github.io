---
emoji: 🚀
title: useEffect란?
date: '2022-10-18 00:00:00'
author: 김지수
tags: 리액트 react 
categories: react
---

# 🚀 useEffect()란?
useEffect() 함수는 React component가 렌더링 될 때마다 특정 작업(side effect)을 실행할 수 있도록 하는 리액트 Hook 입니다. 사이드 이펙트는 컴포넌트가 렌더링 된 이후에 비동기로 처리되어야 하는 부수적인 효과들을 뜻합니다. 이러한 기능으로 인해 함수형 컴포넌트에서도 클래스형 컴포넌트에서 사용했던 생명주기 메서드를 사용할 수 있게 되었습니다.

- componentDidMount: 컴포넌트를 만들고, 첫 렌더링을 다 마친 후 실행.
- componentDidUpdate: 리렌더링을 완료한 후 실행. 즉 render()가 업데이트될 때마다 실행
- compoenntWillUnMount: 컴포넌트를 DOM에서 제거할 때 실행.

## useEffect의 기본 형태
```
useEffect(functio, deps)
```
function 실행하고자 하는 함수
deps 배열의 형태 함수를 실행시킬 조건

### 컴포넌트가 마운트 되었을 때 (나타날 때)
```
useEffect(() => {
    console.log('렌더링 될때마다 실행)
})
```
deps를 생략한다면 해당 컴포넌트가 렌더링 될 때마다 useEffect가 실행되게 됩니다. 만약 맨 처음 렌더링 될 때 한 번만 실행하고 싶다면 deps 위치에 빈 배열을 넣어줍니다.
```
useEffect(() => {
    console.log("맨 처음 렌더링될 때 한 번만 실행");
},[]);
```

### 컴포넌트가 업데이트 되었을 떄 (props, state 변경)
```
useEffect(() => {
    console.log(name);
    console.log("name이라는 값이 업데이트 될 때만 실행");
},[name]);
```
특정값이 업데이트될 때만 실행하고 싶을 때는 deps 위치의 배열 안에 실행 조건을 넣어줍니다. 업데이트뿐만 아니라 마운트 될 때도 실행되므로 업데이트될 때만 실행시키고 싶다면 아래와 같은 방법을 사용합니다.

```
  const mounted = useRef(false);
  useEffect(() => {
    if (!mounted.current) {
      mounted.current = true;
    } else {
      console.log(name);
      console.log("업데이트 될 때마다 실행");
    }
  }, [name]);
```

### 컴포넌트가 언마운트 되었을 때(사라질 때) & 업데이트 되기 직전
```
 useEffect(() => {
    console.log("컴포넌트 나타남");
    console.log(name);
    return () => {
      console.log("cleanUp 함수");
    };
  });
```
useEffect는 함수를 반환할 수 있는데 이 함수를 cleanup이라고 합니다.
언마운트 될 때만 cleanup 함수를 실행시키고 싶다면 deps에 빈 배열을,
특정 값이 업데이트 되기 직전에 cleanup 함수를 실행시키고 싶다면 deps에 해당 값을 넣어주면 됩니다.
```
import React, { useEffect, useState } from "react";

function UseEffect() {
  const [name, setName] = useState("초기 닉네임");

  useEffect(() => {
    console.log("컴포넌트 나타남");
    console.log(name);
    return () => {
      console.log("cleanUp 함수");
    };
  });

  const onClick = () => {
    setName("닉네임 변경");
  };
  return (
    <div>
      {name} <button onClick={onClick}>변경</button>
    </div>
  );
}

export default UseEffect;
```

Effect Hook을 사용하면 함수 컴포넌트에서 side effect를 수행할 수 있습니다.


# 질문 리스트

## Hook은 뭘까? 왜 나왔을까?
리액트 16.8.0부터 훅을 처음으로 지원하게 되었습니다. 리액트에서는 왜 훅을 만들었고 어떤 원리를 차용하고 있을까요?

리액트는 클래스를 제거할 계획은 없습니다.
훅은 리액트 컨셉을 대체하지 않습니다. - 기존 컨셉은 뭘까요?

### Hook의 등장 배경
5년간 React로 컴포넌트를 작성하고 유지하는 동안 부딪혔던 수 많은 문제들을 해결했습니다. 

1. 컴포넌트 사이에서 상태 로직을 재사용하기 어렵습니다.
    컴포넌트간에 재사용 가능한 로직을 붙이는 방법을 제공하지 않습니다. 이전부터 리액트를 사용해왔다면 render props나 고차 컴포넌트와 같은 패턴을 통해 이러한 문제를 해결하는 방법에 익술할 것입니다. 그러나 이런 패턴의 사용은 컴포넌트의 재구성을 강요하며, 코드의 추적을 어렵게 만듭니다. React 개발자 도구에서 다른 추상화에 대한 레이어로 둘러싸인 래퍼지옥을 볼 가능성이 높습니다. 개발자 도구에서 걸러낼 수 있지만, 이 문제의 요점은 상태 관련 로직을 공유하기 위해 좀 더 좋은 기초 요소가 필요했습니다.

    훅을 사용하면 컴포넌트로부터 상태 관련 로직을 추상화할 수 있습니다. 이를 통해 독립적인 테스트와 재사용이 가능합니다. Hook은 계층의 변화 없이 상태 관련 로직을 재사용할 수 있도록 도와줍니다.

2. 복잡한 컴포넌트들은 이해하기 어렵습니다. 
    관리하기 힘들어지는 상태 관련 로직들과 사이드 이펙트가 있는 컴포넌트를 유지보수 해야 합니다. 각 생명주기 메서드에는 자주 관련 없는 로직이 섞여들어가고는 합니다. 예시로 componentDidMount 와 componentDidUpdate는 컴포넌트안에서 데이터를 가져오는 작업을 수행할 때 사용 되어야 하지만, 같은 componentDidMount에서 이벤트 리스너를 설정하는 것과 같은 관계없는 로직이 포함되기도 하며, componentWillUnmount에서 cleanup 로직을 수행하기도 합니다. 함께 변경되는 상호 관련 코드는 분리되지만 이와 연관 없는 코드들은 단일 메서드로 결합합니다. 이로 인해 버그가 쉽게 발생하고 무결성을 너무나 쉽게 해칩니다.

    상태 관련 로직은 한 공간안에 묶여 있기 때문에 이런 컴포넌트들을 작게 분리하는 것은 불가능하며 테스트하기도 어렵습니다. 이와 같은 문제를 해결하기 위해 생명주기 메서드를 기반으로 쪼개는 것 보다는, Hook을 통해 서로 비슷한 것을 하는 작은 함수의 묶음으로 컴포넌트를 나누는 방법을 사용할 수 있습니다.

3. 클래스는 어렵습니다.
    Class 사용을 위해서는 자바스크립트의 this 키워드가 어떻게 작동하는지 알아야합니다. 대부분의 다른 언어에서와는 다르게 작동하여 큰 혼란을 주고 코드의 재사용성과 구성을 매우 어렵게 만들고는 했습니다. 훅은 클래스 없이 리액트 기능들을 사용하는 방법을 제시합니다. 개념적으로 컴포넌트는 함수에 더 가깝습ㄴ다. 훅은 함수의 사용을 권장합니다. 명령형 코드로 해결책을 찾을 수 있게 해주며 복잡한 함수형 또는 반응형 프로그래밍 기술을 배우도록 요구하지 않습니다.


## useEffect의 구동 원리는?

## 왜 배열로 넘겨줄까?