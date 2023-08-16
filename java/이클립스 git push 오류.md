# 목차

1. [이클립스 push 오류](#이클립스-push-오류)
2. [해결법](#해결법)

# 이클립스 push 오류

이클립스로 첫 git push 입력 시 git error : Can't connect to any URI 오류가 떴다.

인터넷 검색 후 찾은 내용이다.

# 해결법

## 1. 토큰 만들기 

#### https://github.com/settings/tokens 들어가서 generate new token (classic) 클릭

![](https://velog.velcdn.com/images/ant0410/post/f263112e-24b9-4049-8248-5db8cefeb533/image.png)

## 2. 옵션 설정

![](https://velog.velcdn.com/images/ant0410/post/8370c944-327a-42d0-bfb2-df8f18cd26da/image.png)

#### 2-1. Note 이름은 아무거나 설정

![](https://velog.velcdn.com/images/ant0410/post/d7747446-bf89-4452-8d26-d5a392d402b2/image.png)

#### 2-2. Expiration(유효기간) 은 영구적 또는 원하는 기간 설정

![](https://velog.velcdn.com/images/ant0410/post/85c3dd2a-3afb-4753-9379-6b96f863f12f/image.png)


![](https://velog.velcdn.com/images/ant0410/post/e4351de6-83b8-48a2-9f2e-d4002ea049b5/image.png)

#### 2-3. 허용범위는 구글검색을 해보니 보통 repo/read:org/gist 체크

#### 2-4. Generate token 누르기!

## 3. 생성된 토큰 이클립스 비밀번호에 입력
![Alt text](https://velog.velcdn.com/images/oh_yunseong/post/a5b2cec1-f72c-49dd-8189-81f8be0e64db/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-11-04%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%206.23.05.png)

오류났던 이클립스에서 아이디는 깃허브 아이디, 비밀번호 대신에 생성된 토큰을 입력하면 해결된다.