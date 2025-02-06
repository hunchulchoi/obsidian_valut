---
created: 2024-01-27 17:40
last_modified: 2024-01-27 17:40
tags:
  - js
  - jsdoc
---
###  사용법
```js
/** ... */
```
## 문서주석
#### `@version`
#### `@file ( @fileoverview, @overview)`
#### `@copyright`
#### `@license`
#### `@author`
## 함수주석
#### `@this`
- this 키워드가 참조하는 정보
#### `@constant ( @const)`
- 상수 정보
#### `@description`
- 설명 정보
```js
/**
 * @param {number} a
 * @param {number} b
 * @returns {number}
 * @description Add two numbers.
 */
function add(a, b) {
  return a + b;
}

// 첫줄인 경우 생략 할 수 있다.
/**
 * Add two numbers.
 * @param {number} a
 * @param {number} b
 * @returns {number}
 */
function add(a, b) {
  return a + b;
}
```
#### `@throws ( @exception)`
- 오류나 예외 사항을 나타냄
```js
/**
 * @throws {InvalidArgumentException}
 */
function foo(x) {}

/**
 * @throws Will throw an error if the argument is null.
 */
function bar(x) {}

/**
 * @throws {DivideByZero} Argument x must be non-zero.
 */
function baz(x) {}
```
##### `@param ( @arg,  @argument)`
- 파라미터 정보를 나타낸다.
- `@type` 구문과 동일하게 사용할 수 있다.
- `@param {타입} 파라미터 명 - 설명`
```js
/**
 * @param {string} somebody - Somebody's name.
 */
function sayHello(somebody) {
  alert("Hello " + somebody);
}
```
#### `@callback`
- 콜백으로 받은 인자 및 반환값에 대한 정보를 나타낸다.
- ##### 클래스별
```js
/**
 * @class
 */
function Requester() {}

/**
 * Send a request.
 * @param {Requester~requestCallback} cb - The callback that handles the response.
 */
Requester.prototype.send = function (cb) {
  // code
};

/**
 * This callback is displayed as part of the Requester class.
 * @callback Requester~requestCallback
 * @param {number} responseCode
 * @param {string} responseMessage
 */
```
##### 글로벌
```js
/**
 * @class
 */
function Requester() {}

/**
 * Send a request.
 * @param {requestCallback} cb - The callback that handles the response.
 */
Requester.prototype.send = function (cb) {
  // code
};

/**
 * This callback is displayed as a global member.
 * @callback requestCallback
 * @param {number} responseCode
 * @param {string} responseMessage
 */
```
### `@requires`
- 필요한 모듈이 있음을 나타낸다.
```js
/**
 * This class requires the modules {@link module:xyzcorp/helper} and
 * {@link module:xyzcorp/helper.ShinyWidget#polish}.
 * @class
 * @requires module:xyzcorp/helper
 * @requires xyzcorp/helper.ShinyWidget#polish
 */
function Widgetizer() {}
```
### `@todo`
### `@return ( @returns)`
```js
/**
 * Returns the sum of a and b
 * @param {number} a
 * @param {number} b
 * @returns {number}
 */
function sum(a, b) {
  return a + b;
}
```
### `@since`
- 클래스나 메소드등이 언제 추가 되었는지
### @type
- 변수의 타입을 선언한다.
- `?` nullable `{?number}` - number or null
- `!` non-nullable `{!number}` - number but never null
- optional
	- `@param {number} [num]`
	- `@param {number=} num`
	- `@param {number} [num=1]`
```js
/**
 * @type {string}
 */
var s;

/** @type {Window} */
var win;

/** @type {PromiseLike<string>} */
var promisedString;

// DOM 프로퍼티를 사용하여 HTML 요소를 지정할 수 있습니다
/** @type {HTMLElement} */
var myElement = document.querySelector(selector);
element.dataset.myData = "";

// 유니온 타입
/**
 * @type {string | boolean}
 */
var sb;

// 객체 리터럴 타입
/** @type {{ a: string, b: number }} */
var var9;

/**
 * 맵 같은 object는 임의의 `string` 프로퍼티들을 `number`로 바꿔줍니다.
 *
 * @type {Object.<string, number>}
 */
var stringToNumber;

/** @type {Object.<number, object>} */
var arrayLike;

// 함수
/** @type {Function} */
var fn7;
/** @type {function} */
var fn6;
/** @type {function(string, boolean): number} 클로저 구문 */
var sbn;
/** @type {(s: string, b: boolean) => number} TypeScript 구문 */
var sbn2;

/**
 * @type {*} - 'any' 타입으로 쓸 수 있습니다
 */
var star;
/**
 * @type {?} - 알 수 없는 타입 ('any'와 같습니다)
 */
var question;
```
#### 형변환
```js
/**
 * @type {number | string}
 */
var numberOrString = Math.random() < 0.5 ? "hello" : 100;
var typeAssertedNumber = /** @type {number} */ (numberOrString);
```
### @typedef
- 원하는 형태의 타입을 만들어 재사용 할 수 있다.
```js
/**
 * Person 타입 정의
 * @typedef {Object} Person - 사람
 * @property {string} name - 이름
 * @property {string|number} id - 아이디
 * @property {number} age = 나이
 */

/** @type {Person} */
const person = {
  name: '최훈철',
  id: 327,
  age: 47,
};
```
### @template
### @class ( @constructor)
### @extends ( @arguments)
### @enum
## DOM
```js
// 태그 이름 input을 인수로 전달하면서 querySelector를 호출하면 HTMLInputElement 타입이 반환되는 것으로 인식한다.
const $input1 = document.querySelector('input');
// HTMLInputElement 타입의 객체에는 value 프로퍼티가 존재하므로 에러가 발생하지 않는디.
$input1.value = 'hello';

// 클래스 foo를 인수로 전달하면서 querySelector를 호출하면 Element 타입이 반환되는 것으로 인식한다.
const $input2 = document.querySelector('.foo');
// Element 타입의 객체에는 value 프로퍼티가 존재하지 않기 때문에 에러가 발생한디.
$input2.value = 'hello';
//      ~~~~~ 'Element' 형식에 'value' 속성이 없습니다.

// $input3를 HTMLInputElement 타입으로 타입 단언한다.
/** @type {HTMLInputElement} */
const $input3 = document.querySelector('.foo');
$input3.value = 'hello';

// $input4를 HTMLInputElement 타입으로 타입 단언한다.
const $input4 = /** @type {HTMLInputElement} */ (document.querySelector('.foo'));
$input4.value = 'hello';

// $input5를 HTMLInputElement 타입으로 타입 단언한다.
const $input5 = document.querySelector('.foo');
/** @type {HTMLInputElement} */ ($input5).value = 'hello';
```
