# rest 파라미터

- 함수에 전달된 인수들의 목록을 배열로 전달받는다. ,
- 함수 파라미터 자리에 오는 모든 파라미터를 [] 중괄호로 감싸준 파라미터 라는 뜻

## 1.첫번째

```js
function 함수2(...파라미터들) {
  console.log(파라미터들);
}
함수2(1, 2, 3, 4, 5, 6, 7); // [1, 2, 3, 4, 5, 6, 7]
```

## 2. 두번째

```js
function 함수2(a, b, ...파라미터들) {
  console.log(파라미터들);
}
함수2(1, 2, 3, 4, 5, 6, 7); // [3,4,5,6,7]
```

---

# 주의사항

## 1. rest 파라미터는 맨 마지막에 넣어줘야한다.

```js
function 함수2(a, ...파라미터들, b){
  console.log(파라미터들) // 오류
}
```

## 2. 2개 이상 사용금지

```js
function 함수2(a, ...파라미터들, ...파라미터들2){
  console.log(파라미터들)
}
```

---

## 예제

```js
function 글자세기(data) {
  console.log(data);
  var i = [...data];
  console.log(i);

  var c = {};

  i.forEach(item => {
    console.log(item);
    if (c[item] > 0) {
      c[item] = c[item] + 1;
    } else {
      c[item] = 1;
    }
    console.log(c);
  });
}
```

### 기억해야할 것 : { } [item] 은 오브젝트 내에서 데이터를 뽑는 형태이다.
