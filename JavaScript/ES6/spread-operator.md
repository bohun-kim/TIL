# Spread Operator

스프레드 연산자는 배열, 문자열, 객체 등 반복 가능한 객체 (Iterable Object)를 개별 요소로 분리할 수 있는 es6 문법으로,

쉽게 풀어쓰면 "괄호제거 해주는 연산자" 라고 생각하면 쉽다.

예시1)

```js
var 어레이 = ["hello", "world"];
console.log(어레이); // ['hello', 'world']
console.log(...어레이); // hello world
```

예시2)

```js
var arr1 = "world";
console.log(...arr1);
// w o r l d === console.log("w", "o", "r", "l", "d");
console.log(arr1[0]); // w 어레이는 아님
```

---

## 자주 사용하는 곳

## 1. Array 를 합치고, 복사할 때 자주 쓰인다.

```js
var a = [1, 2, 3];
var b = [4, 5];
var c = [...a, ...b]; // [1, 2, 3, 4, 5]
```

### 🚨 주의점

```js
var a = [1, 2, 3];
var b = a;

console.log(a); // [1,2,3]
console.log(b); // [1,2,3]
```

위의 코드를 얕은 복사(shallow copy) 라고 하는데, <br>
데이터가 그대로 하나 더 생성된 것이 아닌 해당 데이터의 메모리 주소를 전달하게 돼서, 결국 한 데이터를 공유하게 되어 데이터를 변경하면 예상치 못한 오류가 발생하고 또 발견하기 어렵기 때문에 deep copy를 사용한다.

```js
var a = [1, 2, 3];
var b = [...a];

a[3] = 4;

console.log(a); // [1,2,3,4]
console.log(b); // [1,2,3]
```

이렇게 작성하게 되면 참조값만 복사된 독립된 값을 가지게 된다. ( = array 를 deep copy 했지만 사실은 shallow copy 한다고 한다. 아래 참조 참고)

> 참조)
> [Javascript 깊은 복사의 함정... 모르고 사용하다 뒤통수 맞았다...](https://helloinyong.tistory.com/267)

## 2. Object 합치기/복사

```js
var o1 = { a : 1, b : 2 };
var o2 = { c : 3, 그리고 o1에 있는거 전부.. }
console.log(o2) // {a: 1, b: 2, c: 3}
```

### 오브젝트 key 값 중복이 발생한다면?

```js
var o1 = { a: 1, b: 2 };
var o2 = { a: 3, ...o1 };
console.log(o2); //{a: 1, b: 2}

var o5 = { ...o1, a: 2 };
console.log(o5); // { a: 2, b:2 }
```

a 라는 키값이 이미 있는 경우 무조건 뒤에 오는 a가 출력된다.

## 3. 함수의 매개변수로 전달할 수 있다.

```js
function 더하기(a, b, c) {
  console.log(a + b + c);
}

var arr = [10, 20, 30];

더하기(...arr); //60
```
