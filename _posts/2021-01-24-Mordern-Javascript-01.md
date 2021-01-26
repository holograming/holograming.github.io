---
title:  "Modern javascript tutorial"
excerpt: ""

categories:
  - modernjavascript
tags:
  - tutorial
  - js
  - javascript
last_modified_at: 2021-01-24
---

## 세미콜론의 사용 여부
- - -
기본적으로 줄바꿈이 있다면 세미콜론은 생략 가능하다. 
(암시적 세미콜론, 세미콜론 자동 삽입[automatic semicolon insertion)이라고 부른다.](https://tc39.es/ecma262/#sec-automatic-semicolon-insertion)

그런데, 가능한 세미콜론을 사용하는것을 권장하고 있다.

[링크](https://ko.javascript.info/structure#semicolon)에서 세미콜론 사용여부에 따라서 결과가 다른것을 확인 할 수 있다.


## 주석
- - -
- // 사용하여 한줄 주석 사용
- /* */ 사용하여 여러줄 주석 사용
- Ctrl + / 한줄 주석의 단축키
- Ctrl + Shift + / 여러줄 주석 단축키   

[링크](https://ko.javascript.info/structure#code-comments)
   
## 엄격 모드
- - -
ES5부터 사용가능.

script의 최상단에 'use strict' 사용시, 스크립트 전체/함수가 모던만 방식을 사용하도록 설정. (선택적 사용 불가)
(링크)[https://ko.javascript.info/strict-mode#ref-372]

만일, 클래스 모듈을 사용 중인 코드라면, 엄격모드가 자동으로 적용됨.
   
## 변수, 상수
- - -
'var', 'let'   
'let' 블럭, 지역 scope   
'var'는 전역, scope가 없음.   
'var'는 선언전에 사용가능 (호이스팅)   

```js
function sayHi() {
  phrase = "Hello";
  alert(phrase);
  var phrase;
}
sayHi();
```
변수는 먼저 선언된 해야만 대입 가능하다. 그런데, var로 선언된 변수는 최상위로 끌어올려지기 때문에 예제처럼 사용 가능함.(hoisting)
   
그러나 엄격모드를 사용시에는, 위처럼 선언전에 사용하는것이 불가능하다.

'const' 는 상수를 나타내는 타입이다.