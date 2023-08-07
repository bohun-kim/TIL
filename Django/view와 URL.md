# Django View

View : 클라이언트에 표시되는 정보를 결정한다.

URL : 해당 정보가 실제 웹사이트에서 표시되는 위치

View 와 URL 은 함께 작동하므로, 본질적으로 웹 사이트의 특정 웹 페이지라 생각할 수 있다.

View 가 한 웹페이지라고 생각하면 되는데 URL 을 통해 라우팅을 해야 화면을 볼 수 있다.

## 2개의 urls.py 파일

1. 프로젝트 수준의 URL 구성
2. 앱 수준의 URL 구성

App url.py --> App view.py --> project.url.py

View.py 경로 리스트는 url patterns 라는 리스트 변수에 정의된다.

## View.py 를 URL 에 연결

### path 함수 사용

#### path 함수 첫번째 인자

- route 함수 호출에 필요한 첫 번째 인수는 실제 경로 (URL patterns 을 포함하는 문자열 코드)
  - Django는 일치하는 문자열 경로를 찾을 때까지, 관련 urlpatterns 리스트를 스캔한다. (예: 'app/')
  - 나중에 실제로 미리 알 수 없는 경로를 받기 위해 동적으로 미리 설정하여 만들 수도 있다.

#### path 함수 두번째 인자

- path 함수의 두 번째 필수 인자 view
- 일치하는 경로를 찾으면 view 인자가 함수 또는 뷰에 연결된다.
  - (일반적으로 관련된 Django 앱의 views.py 파일을 찾는다.)

실제 경로, view 이 2가지가 특정 urls.py 파일 내부에 경로를 정의할 때마다, 고려해야 할 두 가지 주요 인자이다.

이 두가지가 웹 사이트에서 템플릿이나 URL 을 표시하는 실제 경로가 있는 곳이다.

## 어떤 뷰를 보여줘야 할까? (정보는 어디에 표시되고, 표시될 정보는 무엇일까?)

### 추가 선택적 두가지 인수(kwargs, name)

#### kwargs

kwargs 를 딕셔너리 뷰로 전달할 것이고, 유연성을 가진다는 특징이 있다.

```py
def name_and_age(**kwargs): # kwargs 는 생략가능하다.
	print(kwargs)

name_and_age(name="홍길동", age="50")

### 출력값 ###
{'age': '50', 'name': '홍길동'}
```

#### name

Django의 다른 곳에서 참조하기 위해 URL의 이름을 지정한다.

커스텀 정의된 이름을 사용하여 뷰와 URL 경로를 간단히 참조할 수 있는 강력한 기능이다.
