# 기초 백엔드 스터디
## What I learned in week2

## 1.
### 아키텍쳐 패턴
* 아키텍쳐 패턴: 어떤 상황의 소프트웨어 아키텍쳐에서, 일반적으로(자주) 발생하는 문제를 해결하며 유지 보수가 용이한 소프트웨어 구조. 재사용 가능한 솔루션. 그 중 하나인, 'MVC' 패턴에 대해 알아보자.
 MVC는 프로젝트의 구성 요소를 < Model(모델), View(뷰), Controller(컨트롤러) > 세 가지로 역할에 따라 구분하는 패턴이다.(MVC == Model-View-Controller)
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
View : (views.py) 받은 요청과 Model에 저장된 정보를(DB) 이용하여 특정 동작을 수행하고 결과를 반환한다. (*Template을 사용할 경우 Template을 Rendering)
Model : View에서 이루어질 특정 동작에 필요한 데이터를 제공하거나 저장한다.(DB와 상호작용)
Template : 유저에게 보여지는 화면에 대한 - 응답 내용을 가공/관리한다. 
> * url의 구조 
> "http://domain:80/path/myHtml.html?queryParam=value"
> 프로토콜://도메인:포트/경로/쿼리파라미터
> ?뒤의 파라미터를 전달한다.

#### 장고 프로젝트 파일

14페이지’
path(‘admin/‘,admin.kkkk) ===> ‘../‘뒤에 요청이 들어오면 해당 —(views.order)를 실행해라::  아까 url뒤에 ?뒤에 ㅂ붙는 내용이 파라미터니까.. 변수 받으면 해당 함수 실행하는 그런거.
(views.py에 있는 order함수를 실행하게 된다.)
