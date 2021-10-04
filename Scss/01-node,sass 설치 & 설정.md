# 1. CSS Preprocessor (CSS 전처리기)

전처리기는 자신만의 특별한 syntax 를 가지고 CSS를 생성하도록 하는 프로그램이다. <br>
믹스인(mixin), 중첩 셀렉터(nesting selector), 상속 셀렉터(inheritance selector), 기타 등등. 이 특징들을 가지고 CSS 구조를 가독성있고 더 유지보수 하기 좋게 만들어준다.

# 2. Sass (Syntactically awesome style sheet)

Sass는 CSS 전처리기로써 CSS의 한계나 단점을 보완하기 위해 만들어진 CSS 확장 언어이다.

SCSS와 Sass는 불필요한 선택자(Selector)의 과용과 연산 기능의 한계, 구문(Statement)의 부재 등 프로젝트가 커지면서 복잡해지는 CSS 작업을 쉽게 해주며 가독성과 재사용성을 높여주어 유지보수가 쉬워지게 도와준다.

# 3.Sass의 기능 및 도구

  1. 변수

  2. 조건문, 반복문

  3. Mixin

  4. 연산자

  5. Extend

  6. Nesting

  7. Import

위의 기능들로 CSS보다 심플한 표기법으로 CSS를 구조화하여 표현할 수 있다.

# 4. Sass 와 SCSS 차이점

문법을 포함한 여러 차이점이 있지만 간단히 요약하자면 Sass보다 SCSS가 뒤에 나왔고, <br>
여러가지 문법의 차이가 있지만 SCSS가 더 넓은 범용성과 CSS의 호환성 등의 장점으로 SCSS를 사용하기를 권장하고 있다.(공식문법도 SCSS를 기준으로 나와있다고 함) <br> 
따라서 Sass는 통상적으로 SCSS라고 부르기도 하는 것 같다.
둘의 차이에 대한 상세한 내용은 다음 링크에서 확인이 가능하다.

[Sass 와 SCSS 차이점](https://designmeme.github.io/ko/blog/write-sass-with-scss/)

# 5. 주의점

<img src ='https://media.vlpt.us/images/jch9537/post/80177762-ee3d-40d2-9883-bc2d5bfc2775/image.png'/>

CSS pre-processor(전처리기) 는 브라우저에 적용하는 것이 아니라 CSS를 확장해서 쉽고 편리하게 쓰기 위해 쓰는 스크립팅 언어이기 때문에 Sass로 작성한 코드는 컴파일을 해서 일반 CSS의 문법으로 바꾼 뒤 사용 가능하다.