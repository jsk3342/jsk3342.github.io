---
emoji: 🔮
title: 디자인 시스템
date: '2022-11-13 00:00:00'
author: 김지수
tags: 디자인 시스템
categories: design
---

# 디자인시스템

### 공부해야할 것 및 체크리스트

1. 디자인 시스템이란 무엇인가?
2. 어떤 디자인 시스템을 구축하는게 좋을까?
   1. 필요한 디자인 컴포넌트 나열 (checkbox 던 뭐던, color token까지 개발할지?)
3. UI 라이브러리를 개발하기위해서는 어떤 개발 방법론이 있는가?
   1. - headless ui

      1. 왜 headless 컴포넌트로 트랜드가 넘어가게 되었을까? 진심으로 이해하기

      ```jsx
      const { value, setValue } = useRadio(); <- 로직에 대한걸 hook 이나 함수로 숨김

      return <>
       <input type="radio" value={value} onChange={setValue} />
      </>
      ```

   2. presentaional component & container component

      ```jsx
      <Container> <- 데이터를 핸들링 하는부분
      	 <Presentational /> <- UI 부분
      </Container>
      ```

   3. stateful component & stateless component
4. UI 라이브러리를 배포하고 사용하기 위해서는 어떻게 해야할까?
   1. npm registry
   2. npm registry deploy
   3. type 까지
5. storybook에서 확인 할 수 있게

### 우리의 최종 목표

- 디자인 시스템 컴포넌트를 개발 및 npm에 배포한다. (멘토도 이걸 사용할 수 있게)
- 배포된 디자인 시스템을 바탕으로 챌린저스 모킹 웹을 개발한다.
