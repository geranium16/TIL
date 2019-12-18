# Python 기초

> 대/소문자 / 띄어쓰기 / 스펠링 지켜주기!
>
> 파이썬 다운로드 : Download [Windows x86-64 executable installer](https://www.python.org/ftp/python/3.8.0/python-3.8.0-amd64.exe)      ->add어쩌고저쩌고 체크 -->배쉬에서 python --version  (확인) macOS python3 --version

``` sh
<Bash>
$ python --version // 버전확인
$ code python_basic.py //으로 현재폴더에서 파이썬코드만들기
$ python python_basic.py // 배쉬에 출력
```

### 1. 저장

- 숫자 : double , int 나눌 필요 없다.

``` python
number = 123
number_two=-456
number_three=7.89
# print(number)
# print(number_two)
# print(number_three)
print(f'{number} 기준 미세먼지 농도는 {number_two}이고 {dust}입니다.')

```

- 글자 : 따움표로 감싸주면 문자열

``` python
a='ABC'
b='123'
c=123
print(a,b,c,123)
print(type(b),type(c),type(123))
```



- 참/거짓 : True , False 앞 글자는 대문자!!!

``` python
d=True
e=False
print(d,e,type(d),type(e))
```



- 리스트 (배열)

```python
a= [1,2,3,4,"a","b","c"]
print(a)
print(a[0])
print(a[0:3]) // 0~2까지 나옴
print(array[-1]) # c가 나온다. ,-2,-3도 가능하지만 직관적으로 -1만 사용
numbers=list(range(1,5))
print(numbers) # 1~4까지 나온다


```

- Dictionary (map)

``` python
dust = {'영등포구' : 50,'강남구':40 } #'key':value
print(dust['영등포구']) 
dust2=dict(abc=50,cdf=40)  # abc라는 변수(key)에 50을 담아서 dictionary형태로 만든다. '' (X)
print(dust2)
```



- Opensource이용

``` python
import random
choice = random.choice(menu)
```



- if

``` python
x=4
y=2
if x>=1 and x<=3 :
    print(x+y)
elif y>=1 or y<=3 :
    print(y-x)  
else:
    print(x-y)


```

- 반복 (while) & (for)

``` 
n=0
while n<3: 
    print(f'출력{n}')
    n=n+1

```

```
numbers=list(range(10))
for number in numbers:
    print(number)
# number가 numbers리스트 끝날때까지 올라감
```





















































