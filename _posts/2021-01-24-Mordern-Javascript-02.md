---
title:  "Modern javascript tutorial"
excerpt: ""

categories:
  - modernjavascript
tags:
  - tutorial
  - js
  - javascript
last_modified_at: 2021-01-26
---

## 형변환
- - -
타입 확인 방법

```javascript
typeof value
```

문자형 변환
String(value)
```javascript
let value = true; // boolean
value = String(value); // 변수 value엔 문자열 "true"가 저장됩니다.
```

숫자형 변환
Number(value)
```javascript
let str = "123"; // string
let num = Number(str); // 문자열 "123"이 숫자 123으로 변환됩니다.
```

항상 숫자형 변환의 성공되는것이 아니기 때문에, 규칙이 있다. 예로 문자의 경우, 공백을 제거 후 숫자만 있을 경우, 숫자로 변환된다. 변환 실패시 undefined(NaN)이 된다.

```javascript
Number("   123   "); // 123
Number("123z");      // NaN ("z"를 숫자로 변환하는 데 실패함)
Number(true);        // 1
Number(false);       // 0
```

불리언 변환
Boolean(value)
```javascript
Boolean(1); // 숫자 1(true)
Boolean(0); // 숫자 0(false)
Boolean("hello"); // 문자열(true)
Boolean(""); // 빈 문자열(false)
Boolean("0"); // true
Boolean(" "); // true: 공백은 비어있지 않은 문자열
```
"0" 은 true이고, " "도 true 이다. 주의하자!
   

## 비교연산자
- - -
왜 비교연산자를 알아야 하나?!
js는 모든 변수들에 대해서 비교 연산자 사용이 가능하다

```javascript
Boolean('2' > 1) // 문자열과 숫자 비교임에도 비교연산자 지원.
Boolean("applie" > "pineapple") // false, a < p 
Boolean("2" > "12") // true, 2 > 1 
```
문자와 숫자 비교시 문자를 숫자로 형변환하여 비교한다. 문자와 문자 비교시 각 글자의 unicode 값을 순차적 비교한다.

기본연산자에서 변수를 숫자로 형변환하여 비교연산을 지원한다. (문자비교시에는 Unicode로 변환된 값으로 비교를 한다. "A" < "a" 가 true이다.). 형변환하지 않아도 숫자로 형변환하여 비교가 가능하다는 것이다.

그럼 형변환 고려하여, 엄격하게 비교연산자를 사용하는 방법도 있다.
    
```js
Boolean( 0 === false ); // false, 피연산자의 형이 다르기 때문입니다.
```

그리고 null과 undefined 의 비교 연산자 동작에 대해서도 알아두자
```js
Boolean(null === undefined ); // false, 타입 불일치
Boolean(null == undefined); // true, undefined는 null하고만 일치
Boolean( null > 0 );  // (1) false
Boolean( null == 0 ); // (2) false
Boolean( null >= 0 ); // (3) true
Boolean( undefined > 0 ); // NaN은 비교 연산자시 false
Boolean( undefined < 0 ); // NaN은 비교 연산자시 false
Boolean( undefined == 0 ); // undefined는 null하고만 true 그외는 false
```