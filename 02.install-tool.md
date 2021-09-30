# 필요한 툴 설치

## 1. 터미널

 <br>

## 2. Git

### 2-1. Git 버전 확인

    git --version

### 2-2. [Git 설치 홈페이지](https://git-scm.com/book/ko/v2/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-Git-%EC%84%A4%EC%B9%98)

<br>

## 3. Node.js 설치

### 3-1 Node.js 란

- node.js 는 자바스크립트를 실행할 수 있는 환경이다.
- 자바스크립트는 브라우저 위에서 동작하는 웹페이지나 웹어플리케이션 이었다.
- node.js 덕분에 브라우저 밖 (운영체제 등) 에서도 자바스크립트 코드를 실행할 수 있게 됐다. <br>
  (원래 자바스크립트는 스크립트 언어로 웹 브라우저 안에서만 실행이 가능하며 브라우저 없이 단독으로 실행할 수 없다.)
- 어느 곳에서나 자바스크립트로 프로그래밍이 가능하게 하는 프레임워크 이다.

### 3-2 npm 이란

- 라이브러리 (패키지) 들을 관리하기 쉽게 도와주는 것이 npm 이다.
- npm : 라이브러리를 설치 & 업데이트 한다.
- npx : 라이브러리를 실행 한다.

### 3-3. Node,npm 버전 확인

    node -v

    npm -v

### 3-4. [Node.js 설치 홈페이지](https://nodejs.org/ko/) <br>

### 3-5 Node.js , npm 업데이트

    <Node.js>
    1. npm cache clean -f  -> npm 캐시 제거
    2. npm install -g n -> Node.js 버전을 관리할 수 있는 n 모듈 설치
    3. n stable : 안정 버전
       n latest : 최신 버전
       n lts : lts 버전

    <npm>
    1. sudo npm istall -g npm

<br>

## 4. yarn

### 4-1. yarn 이란

- yarn은 페이스북에서 만들어진 패키지 매니저 이다.
- npm 에서 취약한 점(버전 관리 , 성능 , 보안)을 보완해서 만들어졌다.
- npm package.json 을 유지하면서 npm과 호환 가능하다.

### 4-2. yarn 설치

    터미널에 brew install yarn 을 입력하면 설치할 수 있다. (단, brew 설치 되어 있어야함)

### 4-3. 오류 대처법

<img width="497" alt="스크린샷 2021-09-30 오후 9 00 00" src="https://user-images.githubusercontent.com/75374915/135451411-50b16912-5277-4fc2-9995-029f026cac3c.png">

    설치하면 이런 오류가 나올 수 있는데 brew 나 yarn 을 옛날에 깔았다가 데이터가 남아 있어 오류가 날 가능성이 크다 이 때 이 명령어를 써주면 된다.

    1. brew 코어 디렉토리 삭제
    rm -fr $(brew --repo homebrew/core) 명령어 입력

    2. brew install yarn  입력하면 설치가 완료된다.

    3. brew --version 으로 버전확인

    [다른 오류 참고](https://velog.io/@jscn/error-npmyarn-%EC%98%A4%EB%A5%98-error-An-unexpected-error-occurred)

<img width="414" alt="스크린샷 2021-09-30 오후 9 06 09" src="https://user-images.githubusercontent.com/75374915/135451999-9be09b05-c6a0-48c6-958d-0ed031168091.png">
<br>

## 5. brew

### 5-1. brew 설치

    [brew 설치 홈페이지](https://brew.sh/)

    -터미널에 붙여넣기-
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" <br>

### 5-2. brew 오류 대처법

![image](https://user-images.githubusercontent.com/75374915/135452613-919e6001-dd51-4eda-82d6-1330b2136ed2.png)

    Warning: /opt/homebrew/bin is not in your PATH. 오류가 뜰 수 있는데 이유는 아직 PATH 등록이 되지 않아서 이다.

    해결방법 : echo 'export PATH=/opt/homebrew/bin:$PATH' >> ~/.zshrc 명령어 입력

    확인방법 : 1. vi ./.zshrc 입력 하면 맨 밑에 한줄이 자동으로 입력 :q 를 쓰고 엔터 누르면 나옴
             2. source ~/.zshrc 입력하여 zshrc 반영

    brew --version 으로 확인
    brew update 로 업데이트 가능

    참고 블로그 : https://shanepark.tistory.com/45
