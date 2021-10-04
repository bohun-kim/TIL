# 1. icon font 만들기

실제 오늘의 집 사이트에 가보면 날것의 html에 svg 코드가 그대로 있다 그건 react에서 간단하게 구현이 가능하기 때문에 되는 것이고 일반 html을 사용하려면 font 처럼 바꿔주어야 한다.

# 2. icon font 순서

## 2-1. [IcoMoon App](https://icomoon.io/app/#/select) 들어가기

<img width="1440" alt="스크린샷 2021-10-01 오후 2 54 55" src="https://user-images.githubusercontent.com/75374915/135572674-2ec25581-c90a-469d-b7c4-edd7b3b477a1.png">


들어가서 import icons 로 내가 사용할 svg 파일을 넣어주면 아이콘들이 나열된다. 그 후에 generate Font를 눌러주면 아래와 같은 사진이 나온다.

## 2-2. 소문자로 바꿔주기

![](https://images.velog.io/images/bohun-kim/post/b8feb767-bbfc-4370-9c56-9b5167ddbbca/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%202.50.05.png)

맨 처음 generate font 를 클릭해서 위 사진이 나오면 앞에가 대문자일텐데 소문자 또는 icon-menu 이런식으로 바꿔주고 download 옆에 있는 옵션 버튼을 눌러준다.

## 2-3. 옵션 설정하기

![](https://images.velog.io/images/bohun-kim/post/8432ba31-54a7-4ab2-96d2-7aff6c01e7ff/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%202.51.54.png)

누르면 옵션설정 창이 나오는데 이름 , prefix (앞에 이름 붙여주는거) , CSS Selector에서 위 사진과 같이 체크해준다.

## 2-4. 다운로드


![](https://images.velog.io/images/bohun-kim/post/08058aac-9887-493e-99bf-3b7f5aeef742/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%202.52.10.png)

옵션 설정 후 다운로드를 눌러주면 다운 완료다.

## 2-5. 프로젝트 폴더에 적용하기

![](https://images.velog.io/images/bohun-kim/post/abf36386-077e-40e8-9e17-79236b03f1a7/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%203.15.58.png)

다운로드 받은 파일들을 모두 복사하여 화살표 방향대로 프로젝트 파일에 새로운 폴더를 만들어 저장해준다.

## 2-6. style.css 적용

![](https://images.velog.io/images/bohun-kim/post/60f6648b-e37a-45a0-923c-1e0aaa69d04e/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%203.22.40.png)

- 다운로드 받은 icon 파일 안에 style.css 파일이 있는데 안에 내용을 복사해주고
- 내 VStudio 파일 경로 안에 styles 안 base 파일 생성 안 _font.scss 파일을 생성해준다.
- _font.scss 안에 복사했던 내용들을 붙여넣고 scss lint 를 이 페이지 안에서만 안사용하겠다는 주석을 달아준다.

## 2-7. 사진안 경로 지정하기

![](https://images.velog.io/images/bohun-kim/post/73c65b15-4f07-40c1-ac07-c5a9d70c7faa/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%203.29.43.png)

위의 사진을 보면 src 가 있는데 이를 내 경로에 맞게 변경 해주어야한다.

## 2-8. style.css 에 import 해주기

![](https://images.velog.io/images/bohun-kim/post/f58fe48c-01b3-4c02-9ae0-64a40ad154b2/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%203.34.33.png)

- main.scss 에서 @imprt './base/fonts' 경로 지정을 해주고 
- npm run sass 를 해주면 style.css 에 내가 적용할 font-icon들이 있다.

## 2-9. 사용하기

![](https://images.velog.io/images/bohun-kim/post/2cf5829c-3dbc-403a-a724-10db6e86cef5/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%203.39.07.png)

style.css 에 있던 클래스를 가져와서 html에 적어주면 위의 사진처럼 적용한 아이콘을 볼 수 있다.

![](https://images.velog.io/images/bohun-kim/post/5bd5a5de-990d-4019-872c-84cac8eb5503/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%203.42.59.png)

아이콘 변경 전에는 의미없는 태그가 aria-label, 스타일을 지정하여 의미있는 태그로 만들었다.

크기를 변경할 때에는 기본적으로 font 이기 때문에 font-size 속성으로 변경할 수 있다.

# 3. favicon 생성하기

## 3-1. [favicon generator](https://realfavicongenerator.net/) 들어가기

홈페이지 들어가서 select your favicon imgae 를 클릭해주고 변경할 사진을 클릭해주면 아래와 같은 사진이 나온다.

![](https://images.velog.io/images/bohun-kim/post/d2341235-3182-411f-8dae-befa1feaa878/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.15.04.png)


![](https://images.velog.io/images/bohun-kim/post/6e1e9e47-bfa6-455e-aff6-9df12bb1055b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.20.07.png)

색을 지정하고 저장해주면 아래와 같은 사진이 나온다.

![](https://images.velog.io/images/bohun-kim/post/fe76d561-888f-451a-a748-0a2019f14e8b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-10-01%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.21.59.png)

이 코드들을 복사해 주고 html에 붙여준다.

주의점이 넣으려고 하는 favicon의 이미지를 프로젝트 폴더의 root(시작이 되는 디렉토리) 에 넣어주어야 한다.