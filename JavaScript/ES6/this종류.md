# this 의 의미

## 1. 첫번째 경우

### window { } : 모든 전역변수, 함수, DOM을 보관하고 관리하는 전역객체

    (ex : document.getElementById(), alert(), console.log() )

### 전역 this : window { }

```js
console.log(this); //window {}
```

### 함수 안 this : window { }

```js
function 간지나는함수() {
  console.log(this);
}
간지나는함수(); //window { }
```

---

## 2. 두번째 경우

### object > 함수(메소드) > this : 주인에 해당하는 객체

```js
var 오브젝트1 = {
  data: "Kim",
  란덤함수: function () {
    console.log("란덤");
  },
};
오브젝트1.란덤함수(); // {data: 'Kim', 란덤함수: ƒ}
```

### object > object > 함수(메소드) > this : 주인에 해당하는 객체

```js
var 오브젝트2 = {
  data: {
    간지함수: function () {
      console.log(this);
    },
  },
};

오브젝트2.data.간지함수(); // {간지함수: ƒ} == data : {}
```

## 어차피 첫번째 , 두번째 경우는 같다.

```js
(1)
  function() {
   console.log(this) // window {}
  }

(2)
  window.간지나는함수 = function(){ console.log() };
```

1번에서 this가 window가 들어있다는 뜻은 window { } 객체 안에 this가 들어있다는 뜻으로 두번째 경우에서 처럼 자기 주인을 의미한다에서 같다고 볼 수 있다.

this는 오브젝트 내의 메소드(함수)에서 사용했을 때 메소드의 주인님 오브젝트를 출력해준다.

---

## 3. 세번째 경우

### constructor 안에서 쓰면 constructor로 새로생성되는 오브젝트라는 의미

```js
function 기계() {
  this.이름 = "Kim";
}
```

this : 기계로부터 새로 생성될 오브젝트들을 의미한다. <br>
this.이름 = 'Kim' : “새로생성되는 오브젝트의 이름 key값에 'Kim'이라는 value를 집어넣어라” 라는 뜻

```js
function 기계() {
  this.이름 = "Kim";
}
var 오브젝트 = new 기계();

console.log(오브젝트); //기계 {이름: 'Kim'}
console.log(오브젝트.이름); //Kim
```

new 키워드를 이용하면 새로운 오브젝트를 꺼낼 수 있다. <br>

새로운 오브젝트는 {이름 : 'Kim'} 이라는 값을 가지고 있다.

---

## 4.네번째 경우

### eventListener 안에서 쓰면 this는 e.currentTarget이라는 의미

```js
document.getElementById("버튼").addEventListener("click", function (e) {
  console.log(e.currentTarget, this, document.getElementById("버튼"));
  // 3개다 동일한 <button id="버튼">dddd</button>
});
```

지금 addEventListener 부착된 HTML 요소를 뜻한다.

### case1) 이벤트리스너 안에서 콜백함수를 쓴다면 this : window { }

```js
document.getElementById("버튼").addEventListener("click", function (e) {
  var 어레이 = [1, 2, 3];
  어레이.forEach(function () {
    console.log(this); // window {} , window {} , window {}
  });
});
```

네번째 경우에서 addEventListner 안에서 사용하면 e.currentTarget 이라고 했는데, <br>

위의 경우 forEach 안에 쌩으로 있는 콜백함수는 그냥 일반함수랑 똑같기 때문에 window가 출력된다.

### case2) 오브젝트 안에서 콜백함수를 쓴다면 this : window { }

```js
var 오브젝트 = {
  이름들: ["김", "이", "박"],
  함수: function () {
    오브젝트.이름들.forEach(function () {
      console.log(this);
    });
  },
};
console.log(오브젝트.함수()); // window {}, window {}, window {}
```

### case3) 오브젝트 안에서 콜백함수 arrow function을 쓴다면 this : 자기를 포함하고 있는 { }

```js
var 오브젝트 = {
  이름들 : ['김', '이', '박'];

  함수 : function(){
      오브젝트.이름들.forEach(() => {
        console.log(this)
// {이름들: Array(3), 함수: ƒ}, {이름들: Array(3), 함수: ƒ}, {이름들: Array(3), 함수: ƒ}
      });
  }
}
```

- arrow function은 외부에 있던 this를 그대로 내부로 가져와서 사용하는 함수
- arrow function은 한 단계 위 콘텍스트의 this를 사용한다.

## 정리

> function() {} 의 this 는 동적으로 실행 컨텍스트를 가져 항상 자신을 감싸고 있는 주체를 값으로 가지고,
> <br><br>
> arrow fucntion 의 this 는 정적으로 실행 컨텍스트를 가지기 때문에 항상 호출된 this의 상위 객체를 값으로 가진다.
