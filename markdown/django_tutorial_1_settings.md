## Creating a Django project

코드를 저장하고 싶은 디렉토리로 이동한 다음 다음 명령을 실행한다.

```
$ django-admin startproject mysite(내가 원하는 이름 충돌되지 않게)
```

**!! 서버의 document root에 코드를 직접 저장하는 것은 보안 상 좋지 않음**

```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```

startproject가 다음과 같은 파일, 디렉토리를 만든다.

- manage.py : command-line utility (참고 :  [django-admin and manage.py](https://docs.djangoproject.com/en/2.0/ref/django-admin/).)
- 내부 myste/ : Python package 로써 project에 사용하게 된다. (e.g. **mystie.urls**)
- init.py : 빈 파일로써 이 디렉토리가 패키지 임을 알린다.
- settings.py : Django project 설정에 관련된 파일 (참고 :  [Django settings](https://docs.djangoproject.com/en/2.0/topics/settings/). )
- urls.py : Django project URL 선언 (참고 :  [URL dispatcher](https://docs.djangoproject.com/en/2.0/topics/http/urls/).)
- wsgi.py : 진입점 WSGI-compatible web servers to serve your project.

```
$ python manage.py runserver
```

위 명령을 실행하면 Django 개발 서버(python으로 짜여진 가벼운 웹서버)를 실행하는 것이다. 

**!! 이 개발 서버는 개발할 때만 사용해라**

 <http://127.0.0.1:8000/>  이 곳을 방문하면 서버가 정상적으로 작동하는 것을 알 수 있다.



## Creating App

하나의 프로젝트에 여러 앱이 들어 갈 수 있다. 

하나의 앱은 여러프로젝트 내에 속 할 수 있다.

프로젝트 내에 app 을 만들기

```
$ python manage.py startapp polls(app 이름)
```

```
polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py
```

다음과 같은 디렉토리가 만들어 진다.



## View 작성하기

polls/view.py 파일을 연다.

```
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

다음과 같은 코드를 작성한다. 이러한 view를 call 하기 위해 URL에 mapping 해야한다.

이를 위해서는 URLconf가 필요하다. poll directory에서 **urls.py** 라는 파일을 만든다.

```
polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    urls.py
    views.py
```

그럼 다음과 같이 디렉토리가 만들어질 것이다.

urls.py에 다음과 같은 코드를 작성한다.

```
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

그 다음은 root URLconf 가 polls.urls module를 가르키도록 한다. 

mysite/urls.py 파일을 연다. 

add an import for `django.urls.include`and insert an [`include()`](https://docs.djangoproject.com/en/2.0/ref/urls/#django.urls.include) in the `urlpatterns` list

```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]
```

include() 함수는 다른 URLconf 들을 참조할 수 있도록 도와줍니다.

```
$ python manage.py runserver
```

잘 적용 됬는지 확인하기 위해 서버를 실행하고  <http://localhost:8000/polls/> 로 이동합니다.

path() 함수는 4개의 인자를 입력받습니다. route, view (필수) kwargs, name (선택)

- route : URL patter을 포함하는 string
- view : 장고가 매칭되는 패턴을 찾으면 그거에 해당하는 view function을 호출함 



## 데이터 베이스 설치



