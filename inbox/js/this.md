---
created: 2024-02-04 15:29
last_modified: 2024-02-04 15:29
tags:
  - js
---
# call
>	`func.call(thisAtg[, arg1[, arg2[, ...]]])`

- thisArg:  func호출에 제공되는 this의 값
- arg1, arg2,... func에 호출되어야 하는 인수
# apply
> `func.apply(thisArg, [argsArray])`

- thisArg:  func호출에 제공되는 this의 값
- argsArray: func이 호출되어야 하는 인수를 지정하는 유사 배열 객체
# bind
> `func.bind(thisAtg[, arg1[, arg2[, ...]]])`
- thisArg:  func호출에 제공되는 this의 값
- arg1, arg2,... func에 호출되어야 하는 인수
- bind는 새롭게 바인딩한 함수를 만든다.
- binding한 함수는 원본 함수 객체를 감싸는 함수이다.
- bind() 결과를 변수에 할당하여 호출하는 형태로 사용한다.