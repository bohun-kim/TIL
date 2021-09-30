# React 란 ❓

React 는 페이스북에서 만든 자바스크립트의 라이브러리 중 하나로 [사용자의 인터페이스](https://ko.wikipedia.org/wiki/%EC%82%AC%EC%9A%A9%EC%9E%90_%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4)를 만들기 위해 사용된다. <br>

# 라이브러리와 프레임워크 차이 ✅

## 라이브러리

> 개발 시 사용되는 프로그램의 구성요소로, 공통으로 사용될 수 있는 특정한 기능을 모듈화

- 다른 사람들이 만들어놓은 것을 내가 가져와서 쓰는 것
- 우리가 원하는 재료들을 골라서 입맛에 맞게 집을 지을 수 있음.
- 작은 단위, 작은 도메인 안에서 자신의 원하는 작은 부분을 구현. 따로 정해진 골격이 없다.
- 배우는 시간이 상대적으로 짧다.
- ex. 리액트

## 프레임워크

> 소프트웨어의 구체적 기능들에 해당하는 부분의 설계와 구현을 재사용 가능하도록 협업화된 형태로 제공하는 소프트웨어 환경

- 다른 사람들이 만들어놓은 코드 안에 내가 들어가는 것
- 집의 구조/철제물이 완성된 완성품
- 다양한 기능들이 한 번에 묶어져서 제공이 되므로 정해진 골격 안에서 원하는 기능을 구현해야 함
- 배우는 데 시간이 오래 걸림
- ex. 앵귤러

## React의 특징 👏

### 1. JSX (JavaScript XML)

#### 1-1 JSX 란?

JSX는 자바스크립트의 확장하여 UI가 어떻게 보일지 정의하는 문법이다. [XML](http://www.tcpschool.com/xml/xml_intro_basic)과 비슷하다. <br><br> 리액트 컴포넌트 파일에서 XML 형태로 작성한 코드는 브라우저에서 실행되기 전에 코드가 [번들링](https://tech.weperson.com/wedev/frontend/bundling-transpiler/#%E1%84%87%E1%85%A5%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A5-bundler)되는 과정에서 바벨을 사용하여 JSX 문법을 일반 자바스크립트 형태의 코드로 변환된다.

```js
function App() {
  return (
    <div>
      Hello <b>react</b>
    </div>
  )
}
```

위의 코드가 아래와 같은 형식으로 변환된다.

```js
function App() {
    return React.createElement('div', null , 'Hello' , React.createElement('b',null 'react'))
}
```

컴포넌트를 렌더링 할 때 마다 위코드처럼 매번 React.createElement 함수를 사용해야 한다면 매우 불편하기 때문에 JSX를 사용하면 편하게 UI 렌더링을 할 수 있다.

### 2. Virtual(가상) DOM

> 브라우저가 HTML 파일을 읽어와서 화면을 띄워주기 까지 과정을 [critical rendering path](https://tech.weperson.com/wedev/frontend/bundling-transpiler/#%E1%84%87%E1%85%A5%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A5-bundler) 라고 한다. <br><br>
> 렌더링 순서에는 DOM -> CSSOM -> RenderTree -> Layout -> Paint -> Composite 순을 거쳐 화면에 나타내게 되는데 한가지 수정할 것이 생기면 렌더링을 다시 해야하는 비효율적인 상황이 생긴다.
> <br><br>
> 그래서 나온 것이 Virtual Dom 이 생성됐다.

![image](https://elmprogramming.com/images/chapter-5/5.3-virtual-dom/elm-runtime-virtual-dom.svg)

위의 그림처럼, 가상 DOM은 DOM이 생성되기 전, 이전 상태 값과 수정사항을 비교하여 달라진 부분만 DOM에게 한 번에 전달하여 딱 한 번만 렌더링을 진행한다.

![image](https://codingmedic.files.wordpress.com/2020/11/virtualdom.png?w=1024)

빨간 부분에 수정사항이 생겼다면, 가상 DOM이 알아서 달라진 값을 탐지하여 변경하고 최종적인 결과물을 실제 DOM에 전달한다. 만약 가상 DOM이 없었다면, DOM은 렌더링을 처음부터 해야했기 때문에 모든 동그라미가 다 빨간색으로 바뀌었을 것이다.

“직접 DOM에 접근하는 것은 지양해야 한다.”

이는 DOM에 직접 접근해도 문제가 되진 않지만, DOM이 직접 변경된다면 사소한 변경사항에도 전체가 재렌더링 되기 때문에 브라우저에 과부하가 올 수 있다. 따라서 최대한 DOM에 직접 접근하지 말아야 한다, 라고 이해하면 될 것 같다.

### 3. props 속성을 이용한 단방향 데이터 바인딩

![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fcre0nA%2FbtqwZiOSIKf%2FkydEYHBXCY1P9otkQWFwsK%2Fimg.png)

props란 각 컴포넌트는 상위 컴포넌트에서 하위 컴포넌트를 import 하여 연결 되어 있는 구조인데 import 되어 있는 하위컴포넌트에게 상위컴포넌트가 값을 전달 하여 하위컴포넌트에서 사용 할 수 있다. <br>
그리고 각 컴포넌트는 스스로 state라는 값을 가질 수 있는데 이는 개별적인 컴포넌트에서 각기 다르게 상태를 가질 수 있다.

    ```js
     1. <Head er></Head>

     2. <Header title="WEB" sub="WorldWideWeb"></Header>
     ```

### 4. Component 단위 작성

![image](https://i0.wp.com/hanamon.kr/wp-content/uploads/2021/01/%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8.png?resize=1024%2C675&ssl=1)

컴포넌트란 프로그래밍에서 재사용 가능한 각각의 독립된 모듈을 뜻한다. <br><br>
위 그림에서 컴포넌트 기반으로 프로그래밍을 하면 Top, Right, Left 모두 컴포넌트의 조각이라고 말할 수 있다.<br> 이들의 특징은 재 사용할 수 있고, 확장할 수 있어야 한다. 그렇게 만들어진 조각들이 모여 홈페이지를 만든다.

> 참고자료 <br> > [하나몬 - 컴포넌트](https://tech.weperson.com/wedev/frontend/bundling-transpiler/#%E1%84%87%E1%85%A5%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A5-bundler)
