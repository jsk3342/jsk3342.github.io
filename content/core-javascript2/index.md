---
emoji: ๐ฎ
title: ์คํ ์ปจํ์คํธ
date: '2022-10-23 00:00:00'
author: ๊น์ง์
tags: ์๋ฐ์คํฌ๋ฆฝํธ core-javascript
categories: ์๋ฐ์คํฌ๋ฆฝํธ
---

# ์คํ ์ปจํ์คํธ
์คํํ  ์ฝ๋์ ์ ๊ณตํ  ํ๊ฒฝ ์ ๋ณด๋ค์ ๋ชจ์๋์ ๊ฐ์ฒด๋ก, ์๋ฐ์คํฌ๋ฆฝํธ์ ๋์  ์ธ์ด๋ก์์ ์ฑ๊ฒฉ์ ๊ฐ์ฅ ์ ํ์ํ  ์ ์๋ ๊ฐ๋์๋๋ค.์๋ฐ์คํฌ๋ฆฝํธ๋ ์ด๋ค ์คํ ์ปจํ์คํธ๊ฐ ํ์ฑํ๋๋ ์์ ์ ์ ์ธ๋ ๋ณ์๋ฅผ ์๋ก ๋์ด์ฌ๋ฆฌ๊ณ (ํธ์ด์คํ), ์ธ๋ถ ํ๊ฒฝ ์ ๋ณด๋ฅผ ๊ตฌ์ฑํ๊ณ , this ๊ฐ์ ์ค์ ํ๋ ๋ฑ์ ๋์์ ์ํํ๋๋ฐ, ์ด๋ก ์ธํด ํน์ดํ ํ์๋ค์ด ๋ฐ์ ํฉ๋๋ค.

์ธ์ด๋ฅผ FPS ๊ฒ์์ ๋น์  ํ์๋ฉด ์ด์ ์  ๋ ๋ฐ๋์ ์ธ๊ธฐ, ๋ชฉํ๋ฌผ๊ณผ์ ๊ฑฐ๋ฆฌ ๋ฑ ๋ณด์ ์ด ๋ค์ด๊ฐ๋ ๊ฒ ์ฒ๋ผ ์๋ฐ์คํฌ๋ฆฝํธ๋ ์์์ ์กฐ์  ๋์ง๋ง C์ธ์ด๋ ์ผ์ผ์ด ์๊ฐํ์ฌ ์์ฑํด์ผ ํฉ๋๋ค.

์ด์ฒ๋ผ ์๋ฐ์คํฌ๋ฆฝํธ๋ ๋ณด์ ์ด ๋ค์ด๊ฐ๊ธฐ ๋๋ฌธ์ ๊ฐ๋ฐ์๋ ์ด๋ค ๋ถ๋ถ์ด ๋ณด์ ์ด ๋ค์ด๊ฐ๊ณ  ๋ณด์ ์ผ๋ก ๋ฐ์ํ๋ ์ฌ์ด๋ ์ดํํธ๋ฅผ ํ์ํ๋ ๋ธ๋ ฅ์ด ํ์ํฉ๋๋ค.

## ์คํ ์ปจํ์คํธ๋?
๋ณธ๊ฒฉ์ ์ผ๋ก ์์๋ณด๊ธฐ ์  ์คํ๊ณผ ํ์ ๊ฐ๋์ ์์์ผ ํฉ๋๋ค.
๋ ๊ฐ์ง ์๋ฃ๊ตฌ์กฐ๋ ์ฐ์์ ์ธ ๋ฐ์ดํฐ๋ฅผ ํจ์จ์ ์ผ๋ก ์ฒ๋ฆฌํ๊ธฐ ์ํด ๋ฑ์ฅํ์ต๋๋ค.

๋์ผํ ํ๊ฒฝ์ ์๋ ์ฝ๋๋ค์ ์คํํ  ๋ ํ์ํ ํ๊ฒฝ ์ ๋ณด๋ค์ ๋ชจ์ ์ปจํ์คํธ๋ฅผ ๊ตฌ์ฑํ๊ณ , ์ด๋ฅผ ์ฝ ์คํ์ ์์์ฌ๋ ธ๋ค๊ฐ, ๊ฐ์ฅ ์์ ์์ฌ์๋ ์ปจํ์คํธ์ ๊ด๋ จ ์๋ ์ฝ๋๋ค์ ์คํํ๋ ์์ผ๋ก ์ ์ฒด ์ฝ๋์ ํ๊ฒฝ๊ณผ ์์๋ฅผ ๋ณด์ฅํฉ๋๋ค. 
์ฌ๊ธฐ์ '๋์ผํ ํ๊ฒฝ', ์ฆ ํ๋์ ์คํ ์ปจํ์คํธ๋ฅผ ๊ตฌ์ฑํ  ์ ์๋ ๋ฐฉ๋ฒ์ผ๋ก ์ ์ญ๊ณต๊ฐ, eval() ํจ์, ํจ์ ๋ฑ์ด ์์ต๋๋ค. ์๋์ผ๋ก ์์ฑ๋๋ ์ ์ญ๊ณต๊ฐ๊ณผ eval์ ์ ์ธํ๋ฉด ํํ ํจ์๋ฅผ ์คํํ๋ ๊ฒ ์๋๋ค.

์ด๋ค ์คํ ์ปจํ์คํธ๊ฐ ํ์ฑํ๋  ๋ ์๋ฐ์คํฌ๋ฆฝํธ ์์ง์ ํด๋น ์ปจํ์คํธ์ ๊ด๋ จ๋ ์ฝ๋๋ค์ ์คํํ๋ ๋ฐ ํ์ํ ํ๊ฒฝ ์ ๋ณด๋ค์ ์์งํด์ ์คํ ์ปจํ์คํธ ๊ฐ์ฒด์ ์ ์ฅํฉ๋๋ค. ์ด ๊ฐ์ฒด๋ ์์ค ์์ง์ด ํ์ฉํ  ๋ชฉ์ ์ผ๋ก ์์ฑํ  ๋ฟ ๊ฐ๋ฐ์๊ฐ ์ฝ๋๋ฅผ ํตํด ํ์ธํ  ์๋ ์์ต๋๋ค. ์ฌ๊ธฐ์ ๋ด๊ธฐ๋ ์ ๋ณด๋ค์ ๋ค์๊ณผ ๊ฐ์ต๋๋ค.

- VariableEnvironment : ํ์ฌ ์ปจํ์คํธ ๋ด์ ์๋ณ์๋ค์ ๋ํ ์ ๋ณด + ์ธ๋ถ ํ๊ฒฝ์ ๋ณด ์ ์ธ ์์ ์ LexicalEnvironment์ ์ค๋์ท์ผ๋ก, ๋ณ๊ฒฝ ์ฌํญ์ ๋ฐ์๋์ง ์์.
- LexicalEnvironment : ์ฒ์์๋ VariableEnvironment์ ๊ฐ์ง๋ง ๋ณ๊ฒฝ ์ฌํญ์ด ์ค์๊ฐ์ผ๋ก ๋ฐ์๋จ.
- ThisBinding : this ์๋ณ์๊ฐ ๋ฐ๋ผ๋ด์ผ ํ  ๋์ ๊ฐ์ฒด.

## VariableEnvironment
VariableEnvironment์ ๋ด๊ธฐ๋ ๋ด์ฉ์ LexicalEnvironment์ ๊ฐ์ง๋ง ์ต์ด ์คํ ์์ ์ค๋์ท์ ์ ์งํ๋ค๋ ์ ์ด ๋ค๋ฆ๋๋ค. ์คํ ์ปจํ์คํธ๋ฅผ ์์ฑํ  ๋ VariableEnvironment์ ์ ๋ณด๋ฅผ ๋จผ์  ๋ด์ ๋ค์, ์ด๋ฅผ ๊ทธ๋๋ก ๋ณต์ฌํด์ LexicalEnvironment๋ฅผ ๋ง๋ค๊ณ , ์ดํ์๋ LexicalEnvironment๋ฅผ ์ฃผ๋ก ํ์ฉํ๊ฒ ๋ฉ๋๋ค. VariableEnvironment์ LexicalEnvironment์ ๋ด๋ถ๋ environmentRecord์ outer-EnvironmentReference๋ก ๊ตฌ์ฑ๋ผ ์์ต๋๋ค. 

## LexicalEnvironment
environmentRecord์ outer-EnvironmentReference๋ก ๊ตฌ์ฑ๋ผ ์์ต๋๋ค. 
์ดํ์, ๋ฌธ๋งฅ์ ๋ผ๋ ์๋ฏธ๋ฅผ ๋ด๊ณ  ์๊ธฐ์ ๋ด๋ถ ์ ๋ณด์ ์ธ๋ถ ํ๊ฒฝ ์ฐธ์กฐ ์ ๋ณด๊ฐ ๊ธฐ๋ก๋ ๊ฐ์ฒด ์ ๋๋ก ์ดํดํ๋ฉด ๋๊ฒ ์ต๋๋ค. 

### environmentRecord์ ํธ์ด์คํ
environmentRecord์๋ ํ์ฌ ์ปจํ์คํธ์ ๊ด๋ จ๋ ์ฝ๋์ ์๋ณ์ ์ ๋ณด๋ค์ด ์ ์ฅ๋ฉ๋๋ค. ์ปจํ์คํธ๋ฅผ ๊ตฌ์ฑํ๋ ํจ์์ ์ง์ ๋ ๋งค๊ฐ๋ณ์ ์๋ณ์, ์ ์ธํ ํจ์๊ฐ ์์ ๊ฒฝ์ฐ ๊ทธ ํจ์ ์์ฒด, var๋ก ์ ์ธ๋ ๋ณ์์ ์๋ณ์ ๋ฑ์ด ์๋ณ์์ ํด๋นํฉ๋๋ค. ์ปจํ์คํธ ๋ด๋ถ ์ ์ฒด๋ฅผ ์ฒ์๋ถํฐ ๋๊น์ง ์ญ ํ์ด๋๊ฐ๋ฉฐ ์์๋๋ก ์์งํฉ๋๋ค.
๋ณ์ ์ ๋ณด๋ฅผ ์์งํ๋ ๊ณผ์ ์ ๋ชจ๋ ๋ง์ณค๋๋ผ๋ ์์ง ์คํ ์ปจํ์คํธ๊ฐ ๊ด์ฌํ  ์ฝ๋๋ค์ ์คํ๋๊ธฐ ์ ์ ์ํ์๋๋ค. ์ฝ๋๊ฐ ์คํ๋๊ธฐ ์ ์์๋ ๋ถ๊ตฌํ๊ณ  ์์ง์ ์ด๋ฏธ ํด๋น ํ๊ฒฝ์ ์ํ ์ฝ๋์ ๋ณ์๋ช๋ค์ ๋ชจ๋ ์๊ณ  ์์ต๋๋ค. ๊ทธ๋ ๋ค๋ฉด ์์ง์ ์ค์  ๋์ ๋ฐฉ์ ๋์ ์ '์์ง์ ์๋ณ์๋ค์ ์ต์๋จ์ผ๋ก ๋์ด์ฌ๋ ค๋์ ๋ค์ ์ค์  ์ฝ๋๋ฅผ ์คํํ๋ค'๋ผ๊ณ  ์๊ฐํ์ฌ ํธ์ด์คํ์ด๋ผ๋ ๊ฐ๋์ด ๋ฑ์ฅํฉ๋๋ค. ๋์ด์ฌ๋ฆฌ๋ค๋ ์๋ฏธ๋ก ๋ณ์ ์ ๋ณด๋ฅผ ์์งํ๋ ๊ณผ์ ์ ๋์ฑ ์ดํดํ๊ธฐ ์ฌ์ด ๋ฐฉ๋ฒ์ผ๋ก ๋์ฒดํ ๊ฐ์์ ๊ฐ๋์๋๋ค. ์ค์ ๋ก ๋์ด์ฌ๋ฆฌ์ง๋ ์์ง๋ง ํธ์์ ๋์ด์ฌ๋ฆฐ ๊ฒ์ผ๋ก ๊ฐ์ฃผํ์๋ ๊ฒ์ด์ฃ .

์ด๋ฌํ ๋ฐฉ์์ด ๋์ด์ฌ๋ฆฐ๋ค๋ ํํ ๋ณด๋ค ๋ณ์ ํธ์ถ ์ค๋น๋ฅผ ๋ง์ณค๋ค๋ ์๋ฏธ๋ก ์ ๋ ์ฅ์ , ๋๋ ์ค๋น์๋ฃ reload ๋ผ๊ณ  ํ๊ณ  ์ถ์๋ฐ ์ฌํ์ ์ผ๋ก ์ฝ์๋ ํธ์ด์คํ์ด๋ผ๋ ํํ์ผ๋ก ์ค๋ชํ๊ฒ ์ต๋๋ค.

### ์ค์ฝํ 
์ค์ฝํ๋ ์๋ณ์์ ๋ํ ์ ํจ๋ฒ์์๋๋ค. ES5๊น์ง์ ์์ค๋ ์ค์ง ํจ์์ ์ํด์๋ง ์ค์ฝํ๊ฐ ์์ฑ๋ฉ๋๋ค. ์๋ณ์์ ์ ํจ๋ฒ์๋ฅผ ์์์๋ถํฐ ๋ฐ๊นฅ์ผ๋ก ์ฐจ๋ก๋ก ๊ฒ์ํด๋๊ฐ๋ ๊ฒ์ ์ค์ฝํ ์ฒด์ธ์ด๋ผ๊ณ  ํฉ๋๋ค.

### ์ค์ฝํ ์ฒด์ธ 
outerEnvironmentReference๋ ํ์ฌ ํธ์ถ๋ ํจ์๊ฐ ์ ์ธ๋  ๋น์์ LexicalEnvironment๋ฅผ ์ฐธ์กฐํฉ๋๋ค.



## QNA

### ์คํ ์ปจํ์คํธ๋?
์ธํฐํ๋ฆฌํฐ ์ธ์ด๋ก ์์ฐจ์ ์ผ๋ก ์ฝ๋๊ฐ ์คํ ๋  ๋ ์ฝ๋์ ์คํ ๋ฒ์๋ ๊ธฐ์ค์ ๋ง์ถฐ ๋์ํด์ผ ํ๋๋ฐ ์คํํ  ์ฝ๋์ ์ ๊ณตํ  ํ๊ฒฝ ์ ๋ณด๋ค์ ๋ด๊ณ  ์๋ ๊ฐ์ฒด ์๋๋ค.

### ํธ์ด์คํ์ด๋?


### var let const ์ฐจ์ด?
var๋ ์ฌ ์ ์ธ๊ณผ ์ฌ ํ ๋น์ด ๊ฐ๋ฅํฉ๋๋ค.
let์ ์ฌ ํ ๋น์ผ ๊ฐ๋ฅ ์ฌ์ ์ธ ๋ถ๊ฐ
const๋ ํ ๋ฒ๋ง ๊ฐ๋ฅํฉ๋๋ค.

### ์ฝ ์คํ์ด๋?
์๋ฐ์คํฌ๋ฆฝํธ ์ฝ๋๊ฐ ์คํ๋๋ฉฐ ์์ฑํ๋ ์คํ ์ปจํ์คํธ๋ฅผ ์ ์ฅํ๋ ์๋ฃ๊ตฌ์กฐ์๋๋ค.

### ์ด๋ฒคํธ ๋ฃจํ์ ๋ํด์ ์ค๋ช ์ฝ ์คํ์ ์ฌ์ฉํ์ฌ
์ด๋ฒคํธ ๋ฃจํ๋ ์ฑ๊ธ ์ฐ๋ ๋์ธ ์๋ฐ์คํฌ๋ฆฝํธ๋ฅผ ๋น๋๊ธฐ ์ฒ๋ฆฌ ํ๊ธฐ ์ํด ๋ธ๋ผ์ฐ์ ์ ๋ธ๋ ํ๊ฒฝ์์ ์๋ํ๊ฒ ๋ฉ๋๋ค. ํจ์ ์คํ์ ๊ธฐ์ ์ผ๋ก ์ฝ ์คํ์ ์คํ ์ปจํ์คํธ๋ค์ด ์์ด๊ฒ ๋๊ณ  ๋์ค์ ๋ค์ด๊ฐ ์ปจํ์คํธ๊ฐ ์ ์ผ ๋จผ์  ๋์ค๋ฉด์ ์ฝ๋๋ฅผ ์ฒ๋ฆฌํ๊ฒ ๋ฉ๋๋ค. ์ด๋ ์ฝ๋ฐฑ ํจ์๋ ๋น๋๊ธฐ ํจ์๋ค์ ๋ง๋๊ฒ ๋๋ฉด ์น API์์ ๋๊ธฐ ํ ์คํ์ด ์๋ฃ๋๋ฉด ํ์คํฌ ํ์ ์ค๋นํ๊ณ  ์๋ค๊ฐ ์ฝ ์คํ์ด ๋น์์ง๊ฒ ๋๋ฉด ํ์คํฌ ํ์์ ์ฝ ์คํ์ผ๋ก ์ด๋ํ์ฌ ์ฝ๋๊ฐ ์คํ๋๊ฒ ๋ฉ๋๋ค.

### ๋ง์ดํฌ๋ก ํ์คํฌ ํ

### ๋ฉํฌ๋ก ํ์คํฌ ํ

### ์ค์ฝํ ๋ธ๋ก, ํจ์ ์ฐจ์ด

### ๋ ์์ปฌ ์ค์ฝํ?

### var๋ฅผ ์์ฐ๋ ์ด์ ?

### ํจ์ ์ ์ธ๋ฌธ, ํํ์ ์ฐจ์ด์ ํจ์ ํํ์์ ์ ํธํ๋ ์ด์ ?
๋ ๋ค ํจ์๋ฅผ ์๋กญ๊ฒ ์ ์ํ  ๋ ์ฐ์ด๋ ๋ฐฉ์์ธ๋ฐ, ๊ทธ์ค ํจ์ ์ ์ธ๋ฌธ์ function ์ ์๋ถ๋ง ์กด์ฌํ๊ณ  ๋ณ๋์ ํ ๋น ๋ช๋ น์ด ์๋๊ฒ์ ์๋ฏธํฉ๋๋ค.
ํํ์์ ์ ์ํ function์ ๋ณ๋์ ๋ณ์์ ํ ๋นํ๋ ๊ฒ์ ๋งํฉ๋๋ค.
์ ์ธ๋ฌธ์ ๊ฒฝ์ฐ ๋ฐ๋์ ํจ์๋ช์ด ์ ์๋ผ ์์ด์ผ ํ๋ ๋ฐ๋ฉด, ํํ์์ ์์ด๋ ๋ฉ๋๋ค.

์ค์ง์ ์ธ ์ฐจ์ด๋ ํธ์ด์คํ์ ์์ต๋๋ค. 
์ ์ธ๋ฌธ์ ์ ์ฒด๋ฅผ ํธ์ด์คํํ๊ณ  ํํ์์ ์ ์ธ๋ถ๋ง ๋์ด ์ฌ๋ฆฝ๋๋ค.

๋ค๋์ ์ฝ๋์์ ์๋์น์๊ฒ ๋๋ช์ ํจ์๋ฅผ ์์ฑํ๊ฒ ๋์ด ์ ์ธ๋ฌธ์ผ๋ก ์์ฑํ๊ฒ ๋๋ฉด ๋์ค์ ํ ๋น๋ ๊ฐ์ด ์ด์  ๊ฐ์ ๋ฎ์ด์์ฐ๊ธฐ ๋๋ฌธ์ ๋๋ฒ๊น์ ์ด๋ ค์์ด ๋ฐ์ํฉ๋๋ค.
