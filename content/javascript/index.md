---
emoji: 🔮
title: 배열 메서드
date: '2022-11-01 00:00:00'
author: 김지수
tags: 자바스크립트 core-javascript
categories: 자바스크립트
---

# 배열 내장 메서드를 알아야 하는 이유
데이터의 입출력을 다룰때 편리한 내장 메서드 때문에 배열을 많이 사용하게 됩니다.

편하게 데이터를 가공하기 위해 메서드를 공부해보겠습니다.

## includes

.includes()는 문자열이 특정 문자열을 포함하는지 확인하는 메서드입니다. IE는 Edge부터 지원합니다.

```string.includes( searchString, length )```
searchString : 검색할 문자열로 필수 요소입니다. 대소문자를 구분합니다.
length : 검색을 시작할 위치입니다. 선택 요소로, 값이 없으면 전체 문자열을 대상으로 합니다.