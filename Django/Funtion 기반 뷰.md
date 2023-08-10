# 1. first_app - view.py

```py
from django.shortcuts import render
from django.http.response import HttpResponse

# Create your views here.


def simple_view(request):
    return HttpResponse("Simple View")  # Template HTML 파일에 연결되고, HTML 파일을 반환함
```

# 2. first_app - urls.py

```py
from django.urls import path
from . import views

# path("") 에서 빈 문자열인 이유
#   - 루트 프로젝트 레벨인 urls.py 파일에서 실제로 이러한 뷰가
#   - 무엇에 해당하는지 정의하는 곳이기 때문이다.

# 예)domain.com/first_app/simple_view

urlpatterns = [path("simple_view", views.simple_view)]
```

# 3. my_site - urls.py

```py
from django.contrib import admin
from django.urls import path, include
from . import views

urlpatterns = [
    path("admin/", admin.site.urls),
    path("first_app/", include("first_app.urls")),
    path("", views.home_view),
]
```
