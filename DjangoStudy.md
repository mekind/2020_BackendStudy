- [1. 기본 디텍토리 구조](#1-기본-디텍토리-구조)
  - [1.0 manage.py](#10-managepy)
  - [1.1 프로젝트명 Dir](#11-프로젝트명-dir)
    - [1.1.1 __ init __.py](#111-__-init-__py)
    - [1.1.2 settings.py](#112-settingspy)
    - [1.1.3 urls.py](#113-urlspy)
    - [1.1.4 wsgi.py](#114-wsgipy)

# 1. 기본 디텍토리 구조 

맨 처음에 django-admin startproject {project명}으로 실행하였을 때 결과가 다음과 같다.

    - app
      - manage.py
      - env (개발자에 따라 유무가 다름)
      - app
        - __init__.py
        - settings.py
        - urls.py
        - wsgi.py
    

## 1.0 manage.py 

django가 돌아가기 위한 가장 기본적인 실행을 하는 코드

## 1.1 프로젝트명 Dir

### 1.1.1 __ init __.py

아무것도 쓰여있지 않다. 이 폴더가 파이썬 파일들로 이루어져 있다는 것을 알리는 파일이라고 한다. 

~~사실 아직 이게 무슨 역할을 하는지 잘 모르겠다~~

### 1.1.2 settings.py

말 그대로 설정을 위해 존재하는 파일이다. 

설정할 수 있는 목록은 다음과 같다.

**Development settings**

1. SECRET_KEY : 정보 암호화에 사용되는 비밀키이고 명령어를 통해 임의로 생성한 값이다.
2. DEBUG : django에서의 오류를 출력할지 말지 결정한다. 
3. ALLOWED_HOSTS : 접속할 수 있는 호스트들을 설정한다. (비어 놓으면 모든 호스트 접속 가능)

**Application definition**

1. INSTALLED_APPS : 사용한 앱들을 설정할 수 있다. 기본적으로 admin 및 auth 앱이 설정되어 있다.
2. MIDDLEWARE : request에 대한 동작을 하기 전에 미리 처리하는 과정들이다.(명령어 파싱, 세션관리, csrf, 인증 등)
3. ROOT_URLCONF : 맨 처음로 라우팅을 위해 접근하는 파일이다. 
4. TEMPLATES : template가 저장된 위치 지정
5. WSGI_APPLICATION : 웹서버 관련 파일 지정 

**DB settings**
1.  DATABASES : 연결할 DB를 지정

**Password validation**

1.  AUTH_PASSWORD_VALIDATORS : user password 검사 규칙 

**Internationalization**

1.  LANGUAGE_CODE : 'ko-kr'
2.  TIME_ZONE : 'Asia/Seoul'
3.  USE_I18N : 
4.  USE_L10N
5.  USE_TZ

**Static files**

1. STATIC_URL : static 파일을 저장하는 디렉토리 설정

### 1.1.3 urls.py

라우팅을 하기 위한 설정들은 여기서 코딩

### 1.1.4 wsgi.py

prod 서버에서 실행될 때 사용하는 웹서버 관련 앱을 생성 

