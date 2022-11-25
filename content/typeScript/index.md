---
emoji: 🔮
title: 타입 스크립트
date: '2022-11-25 00:00:00'
author: 김지수
tags: 타입 스크립트 typeScript
categories: 타입스크립트
---

# 목표
- 일반적으로 사용하는 TypeScript 구문 및 패턴을 읽고 이해하기
- 중요한 컴파일러 옵션의 효과 설명하기
- 대부분의 경우 타입 시스템 동작을 올바르게 예측하기
- 간단한 함수, 객체 또는 클래스에 대한 .d.ts 선언 작성하기

## 타입 구성 Composing Types

### 유니언 Unions
유니언은 타입이 여러 타입 중 하나일 수 있음을 선언하는 방법입니다. 예를 들어, boolean 타입을 true 또는 false로 설명할 수 있습니다.

```
type MyBool = true | false;
type WindowStates = "open" | "closed" | "minimized";
type LockStates = "locked" | "unlocked";
type OddNumbersUnderTen = 1 | 3 | 5 | 7 | 9;
```
### 제네릭 Generics
제네릭은 타입에 변수를 제공하는 방법입니다.

```
type StringArray = Array<string>;
type NumberArray = Array<number>;
type ObjectWithNameArray = Array<{ name: string }>;

// @errors: 2345
interface Backpack<Type> {
  add: (obj: Type) => void;
  get: () => Type;
}

// 이 줄은 TypeScript에 `backpack`이라는 상수가 있음을 알리는 지름길이며
// const backpack: Backpack<string>이 어디서 왔는지 걱정할 필요가 없습니다.
declare const backpack: Backpack<string>;

// 위에서 Backpack의 변수 부분으로 선언해서, object는 string입니다.
const object = backpack.get();

// backpack 변수가 string이므로, add 함수에 number를 전달할 수 없습니다.
backpack.add(23);
```

### 구조적 타입 시스템 Structural Type System
TypeScript의 핵심 원칙 중 하나는 타입 검사가 값이 있는 형태에 집중한다는 것입니다.

## 왜 타입스크립트인가?
자바스크립트는 오류를 알기 위해서는 실행 후 런타임 환경에서 에러를 잡을 수 있습니다. 하지만 실시간으로 오류를 감지하지 못하는 인터프리터 언어의 특성 상 바로 바로 버그를 캐치하고 수정할 수 있다면 견고한 프로그래밍이 가능해 집니다. 이를 타입 스크립트가 타입이 다른지, 함수가 존재하는지 등 여러 가지를 실행 전에 판단하여 알려주게 됩니다.