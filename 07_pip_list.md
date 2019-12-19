# 가상환경

> 서로 다른 응용 프로그램은 서로 다른 가상 환경을 사용할 수 있다.  응용 프로그램 A에는 버전 1.0이 설치된  응용 프로그램 B에는 버전2.0이 필요한데 이를 한 버전으로 사용하면 충돌이 일어난다. 이를 막기 위해 A 가상환경 B 가상환경을 만들어 서로 다른 구축환경을 갖을 수 있게 하여 충돌을 막는다.
>
>  pip는 파이썬으로 작성된 패키지 소프트웨어를 설치 · 관리하는 패키지 관리 시스템이다. Python Package Index (PyPI)에서 많은 파이썬 패키지를 볼 수 있다. 

``` shell
python -m venv 가상환경이름 #  : m=moudation /3.5버전이라 별도의 설치 필요x
#-> ls치면 venv가 설치되어있을거임
#*가상 환경을 사용할 때 주의할 점이 있는데, 가상 환경을 만들고 나서 폴더(디렉터리)를 다른 곳으로 이동시키면 활성화가 안 됩니다. 왜냐하면 가상 환경을 활성화하는 activate.bat, Activate.ps1, activate 파일 안에 현재 가상 환경 폴더의 경로가 내장되어 있기 때문입니다.

source venv/Scripts/activate # 새로 킬떄마다 activate (활성화)
pip list # (python에서 쓸수있는 패키지 리스트)
deactivate #종료 
rm -ref venv/ #삭제
pip install requests
pip install beautifulsoup4
python -m pip install --upgrade pip # 업그레이드

pip freeze > requirements.txt # 여기에 사용한 모듈 및 버전을 txt형식으로 저장 
pip install -r requirements.txt # 이 모듈들을 설치할 수 있다.
```



``` python
# 결과: Response [200] 결과물이 잘 나왔따.[400] 결과 실패 'http응답코드 검색'
import requests
from bs4 import BeautifulSoup

url="https://finance.naver.com/marketindex/"

# get 방식으로 url의 내용을 text형식으로 request로 가져옴
request=requests.get(url).text
# 이를 python이 읽을 수 있게 가져온다.
soup=BeautifulSoup(request,'html.parser')

# html파일을 파이썬이 읽을 수 있게 파싱
# print(soup)
# 크롤링 : 사이트에서 찍고 select 뽑기
exchange=soup.select_one("#exchangeList > li.on > a.head.usd > div > span.value")
print(exchange.text) 
```

*tip: github의 레포지토리에 issue에 사진 넣으면 url알아서 만들어줌

*파싱이란? 

내가 원하는대로 데이터를 가공/변환하는 것이다. 보통 HTML 소스를 얻어온 후 내가 원하는 부분만 추출하는 목적으로 쓰인다.

- 보통 가상환경 셋팅한 것은 깃허브에 안올린다. (+기타 비공개자료 만드는 법)

1. http://gitignore.io/ 검색

2. window , flask ,python, venv

3. ``` shell
   code .gitignore  # 숨김 파일 만들기
   ```



flask

사이트: https://www.palletsprojects.com/p/flask/

``` shell
1.pip install flask //flask 설치 최상위폴더에서
2. hello.py 만들기
	from flask import Flask, escape, request
	app = Flask(__name__)

	@app.route('/')
	def hello():
    	name = request.args.get("name", "World")
    	return f'Hello, {escape(name)}!'

3.env FLASK_APP=hello.py flask run // flask 파일이 들어있는 곳에서 bash에 입력
-----> 이상태명 플라스크로 파일열기

if __name__ == "__main__":
    app.run(debug=True) 코드에 붙여주면 위 env 없이 python hello.py 명령으로 열 수 있음
4.render_template추가
5.mkdir templates  # 무조건 templates에다 html넣어야한다. 스펠링 틀리면 안됨
6.cd templates
7.code hi.html
```

``` python
from flask import Flask, escape, request, render_template
app = Flask(__name__)

@app.route('/')
def hello():
    name = request.args.get("name", "World")
    return f'Hello, {escape(name)}!'
    #  env FLASK_APP=hello.py flask run 가 없이 python hello.py만 해도 서버 켜지게함

@app.route('/hi') 
def hi():  # hi라는 곳에 들어가면
    name = "박대현"
    return render_template('hi.html',html_name=name)
    # hi.html을 렌더링해줘 , name이라는 별수를 넘겨주겟다.
# string: 사용할 이름명
@app.route('/greeting/<string:name>/')
def greeting(name):
    def_name=name
    return render_template('greeting.html',html_name = def_name)

@app.route('/cube/<int:num>')
def cube(num):
    
    def_num=num**3
    return render_template('cube.html',def_num=def_num)
     

if __name__ == "__main__":
    app.run(debug=True)

```

*render_template: 템플릿에 사용되는 파일들은 `templates` 디렉터리에 저장되며 일반적으로 .html 파일을 사용합니다. 또한 css 같은 파일들은 `static` 디렉터리에 저장합니다. 어플리케이션 상에서 이러한 html 파일들을 렌더링할 수 있도록 Flask에서는 `render_template`를 제공하는데요. 

- 구버전으로 바꾸는법

1. pip uninstall flask
2. pip freeze 버전확인
3. pip install flask==1.0.0
4. cd flask들가서 다시 실행

