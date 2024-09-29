# 기초 백엔드 스터디
## What I learned in week2

## 1.
### 아키텍쳐 패턴
아키텍쳐 패턴: 어떤 상황의 소프트웨어 아키텍쳐에서, 일반적으로(자주) 발생하는 문제를 해결하며 유지 보수가 용이한 소프트웨어 구조. 재사용 가능한 솔루션. 그 중 하나인, 'MVC' 패턴에 대해 알아보자.   
    MVC는 프로젝트의 구성 요소를  Model(모델), View(뷰), Controller(컨트롤러)  세 가지로 역할에 따라 구분하는 패턴이다.   
    (MVC == Model-View-Controller)
> - Model : DB와 상호작용하는 부분
> - View : 사용자들의 눈에 보이는 부분(사용자와 상호작용하는 부분)
> - Controller : 웹서비스 내부의 동작 논리를 담당하는 부분
각각의 요소들이(M,V,C) 고유한 역할을 하기 때문에 유지보수하기 용이하다.

### MTV 패턴
django는 MTV패턴을 이용한 웹프레임워크이다. (MTC == Model-Template-View)
> - Model : DB와 상호작용하는 부분
> - Template : 사용자들의 눈에 보이는 부분(사용자와 상호작용하는 부분)
> - View : 웹서비스 내부의 동작 논리를 담당하는 부분(흐름 제어)

### 장고의 작동 원리(프로젝트 구조)
User : 서버로 url을 통해 요청request을 보내고 그에 대한 응답response을 받는다.   
URLconf : (urls.py) 받은 url에 대해 서버에서 작동할 view를 매치시켜준다.   
View : (views.py) 받은 요청과 Model에 저장된 정보를(DB) 이용하여 특정 동작을 수행하고 결과를 template에게 반환한다.    
> (*Template을 사용할 경우 Template을 Rendering)     
> return render(request, 'order.html', context)   
Model : View에서 이루어질 특정 동작에 필요한 데이터를 제공하거나 저장한다.(DB와 상호작용)    
Template : 유저에게 보여지는 화면에 대한 - 응답 내용을 가공/관리한다.     
> * url의 구조 
> "http://domain:80/path/myHtml.html?queryParam=value"   
> 프로토콜://도메인:포트/경로/쿼리파라미터   
> ?뒤의 파라미터를 전달한다.

### 장고 프로젝트 파일
* project/config/ 내부에   
settings.py : 장고 설정에 관한 내용 / DB settings 언어, 시간 설정 등등   
asgi.py, wsgi.py : DB 데이터 조회, 저장, 수정, 삭제 / 동적으로 html 파일 만들기   
urls.py : path를 확인하고, 알맞은 어플리케이션의 알맞은 뷰로 연결해준다.   
> path(‘admin/order/‘, views.order) ===> ...order/뒤에 ?파라미터를 받으며, (views.py에 있는 order함수를 실행하게 된다.)   
* project/ 내부에   
manage.py : 터미널을 통해, 미리 작성된 명령을 실행할 수 있게 해준다.    
(다른 폴더들 congif, jungrang… 등에서 서로 함수 불러오고 전달하고 그런걸 중재하는.. 그것들 사이에 기준이 되는 파일이다.)
> sys.path에 managy.py가 위치한 경로 추가해야 함.

#### Start Application in 장고
> 명령어 'django-admin startapp APPNAME' 입력 ===> 3개의 .py파일을 가진 APPNAME 폴더가 생성된다.   
     
 templates은 따로 만들어준다(?)      
 templates에는 html 코드가 들어가며(.html), views 에서 넘겨받은 정보를 이용해 html을 동적으로 생성하기도 한다.
   
#### 장고 MTV 패턴의 큰 흐름
url로 들어와서, 뷰에 넘기고, 필요하면 모델을 부르고, 여차저차 끝났으면 템플릿에 넘긴다.   
(템플릿은 html을 새로 만들거나..받은 내용을 요구에 맞게 가공한다..)

#### 터미널 명령어 몇가지
cd : change directory(파일변경) —> cd venv(venv로 현재 파일 변경)   
cd.. : —> 상위 폴더로 이동   
mkdir : make directory(파일생성) -> mkdir project

#### 2주차 실습
2주차-3.pdf - 21p까지
