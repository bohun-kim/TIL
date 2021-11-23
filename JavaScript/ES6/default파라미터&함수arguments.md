# defalult 파라미터

defalut 파라미터는 파라미터 값을 안적었을 경우 파라미터에 직접 값을 줄 수 있는 방식이다.

```js
function 더하기(a, b = 10) {
  console.log(a + b);
}
더하기(1); // 11 파라미터가 정의되지 않았을 때 등호 오른쪽 값이 발동된다.
```

## 사칙연산 가능

```js
function 더하기(a, b = 2 * 5) {
  console.log(a + b);
}
더하기(1); // 11
```

## 같은 파라미터 대입 가능

```js
function 더하기(a, b = 2 * a) {
  console.log(a + b);
}
더하기(3); // 9
```

## 함수 입력 가능

```js
function 임시함수() {
  return 10;
}
function 더하기(a, b = 임시함수()) {
  console.log(a + b);
}
더하기(3); // 13
```

# 함수 arguments

arguments 는 Array 형태의 객체이며 함수의 모든 파라미터들을 다루고 싶을 때 사용할 수 있다.

> arguments가 length 속성과 더불어 0부터 인덱스 된 다른 속성을 가지고 있지만, Array의 forEach, map과 같은 내장 메서드를 가지고 있지 않다는 뜻

```js
function 함수(a, b, c) {
  console.log(arguments);
  // Arguments(3) [2, 3, 4, callee: ƒ, Symbol(Symbol.iterator): ƒ]
}
함수(2, 3, 4);
```

```js
function 함수(a, b, c) {
  for (var i = 0; i < arguments.length; i++) {
    console.log(arguments[i]);
  }
}
함수(2, 3, 4); // 2, 3, 4
```
