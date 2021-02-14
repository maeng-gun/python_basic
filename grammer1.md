<a href="https://colab.research.google.com/github/maeng-gun/python_basic/blob/main/grammer1.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## 변수와 자료형

### 1. 프로그래밍 입문 의식(?)

* 어떤 프로그래밍 언어를 사용하든, 프로그래밍 실습에 처음 임하는 사람들은 'Hello, World!'를 출력하는 명령어를 써보는 것이 이쪽 업계의 전통이라고...



```python
print('Hello, World')
```

    Hello, World
    

* IDE로 주피터노트북을 사용하는 경우, 마지막 줄에 입력하는 값은 자동으로 출력되도록 설정돼있기 때문에 별도로 print() 함수를 쓸 필요는 없음. (다만, 출력방식이 조금 다름)


```python
'Hello, World'
```




    'Hello, World'



### 2. 변수 할당하기

### 1) 변수(variable)란?
* 어떤 자료값(value)를 컴퓨터의 메모리에 저장한 공간을 의미. 변수의 이름은 해당 저장공간의 주소를 나타냄.
* 변수를 만들때는 특정 변수 이름을 정하고 등호(=)로 자료값을 할당(assignment)한다.
* (주의) 자료값에 문자열을 입력하려면 작은따옴표(')나 큰따옴표(")를 앞뒤로 붙여줘야 함. 안붙일 경우 해당 문자를 변수명으로 인식함
### <center> 변수명 = 자료값 </center>


```python
a = 2
b = '개'
print(a)
print(b)
```

    2
    개
    


```python
c = 개
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-5-756862840014> in <module>()
    ----> 1 c = 개
    

    NameError: name '개' is not defined


### 2) 변수명을 정하는 규칙
* 문자, 숫자, 언더바(_) 로 구성된 단어
* 처음 시작으로 숫자는 올 수 없음
* 이미 파이썬에서 문법적인 요소로 사용중인 keyword 는 사용할 수 없음 (ex. for, if 등)



```python
if = 1
```


      File "<ipython-input-6-773eba7f7781>", line 1
        if = 1
           ^
    SyntaxError: invalid syntax
    


### 3) 변수의 주소값(id)과 변수 참조

* 변수를 생성(할당)하면 실제로는 메모리 상에 주소값이 만들어지는 것이고, 변수명은 해당 주소값의 별명을 붙여주는 것.
* id 함수를 통해 해당 변수의 주소를 알 수 있음



```python
print(id(a))
print(id(b))
```

    10914528
    139686448532736
    

* 새로운 변수명에 기존의 변수를 할당하게 되면 동일한 주소값을 **참조**하게 됨. 이때 원래 변수의 값을 바꾸면, 참조한 변수의 값도 따라서 바뀜


```python
c = a
print(c)
print(id(c))
```

    2
    10914528
    


```python
a = 3
print(a)
print(c)
```

    3
    2
    

### 3. 자료형(type)

#### 1) 자료형이란?
* 모든 데이터는 각각 특정한 자료형에 속해 있음. (좀 더 넓은 의미로는 클래스(class)라고 함. 일종의 '신분'인 셈)
* 파이썬의 경우 변수 생성시 입력된 데이터의 형태를 알아서 판단해 자료형을 지정해 줌 (다른 프로그래밍 언어들은 반드시 자료형을 일일이 지정해줘야 함)
* type() 함수를 통해 특정 자료값 또는 변수의 자료형을 확인 가능


```python
print(type(2))
print(type(1.5))
print(type(b))

e = [1,2,3]
f = (4,5,6)
print(type(e))
print(type(f))
```

    <class 'int'>
    <class 'float'>
    <class 'str'>
    <class 'list'>
    <class 'tuple'>
    

#### 2) 파이썬 자료형
* 자료형은 말 그대로 특정한 자료들을 담는 형식, 그릇을 의미하는데, 사용자가 임의의 자료형을 정의해 만들어낼 수도 있음. (-> 클래스(class)의 생성. 고급 문법에 해당하며, 주로 남이 만들어놓은 클래스를 가져다 쓰게 됨)
* 파이썬에서 기본적으로 제공하는 클래스를 '자료형'이라고 지칭함. 
* 위에서 본 int, float, str, list, tuple 등이 파이선의 기본 자료형임. 이들을 범주별로 묶어보면 크게 **스칼라형**, **문자열**, **컨테이너형**, **시퀀스형**으로 나눌 수 있음


#### 3) 스칼라형

*  숫자나 참/거짓 등 하나의 값을 담는 자료형들의 범주
* **int** : 소수점이 없는 정수(integer) 자료형
* **float** : 소수점이 있는 실수(floating number) 자료형
* **bool** : 참(True)과 거짓(False) 두개의 값만 존재하는 자료형. 주로 조건문의 판단 결과값을 표현하는 경우임
* **NoneType** : 해당 공간에 데이터가 없음(None)을 의미하는 자료형. 주로 외부 데이터를 불러올 때 자료가 담겨있지 않는 부분을 표현하는 경우임.



```python
g = True
h = (a==b)   # == 는 양변이 같다는 것을 의미하는 연산자
print(g, type(g))
print(h, type(h))
```

    True <class 'bool'>
    False <class 'bool'>
    


```python
g = None
print(g, type(g))
```

    None <class 'NoneType'>
    

#### 4) 문자열(str)

* 낱글자, 단어, 띄어쓰기, 기호 등으로 구성된 문자들의 집합. 범주가 아니라 그 자체로 자료형의 하나
* 작은 따옴표(')나 큰 따옴표(")로 둘러싸인 값은 문자열 자료형이 됨. 개별문자간 **순서**를 인식


```python
i = '가'
j = "라"
k = """가나다"""      # 큰 따옴표 세개(""")로도 문자열 표현 가능
l = """그 사람은 "저는 '상호금융자금부' 소속입니다" 라고 말했다.""" # 따옴표를 문자열의 값으로 나타낼 때

print(i,j,k,l)
```

    가 라 가나다 그 사람은 "저는 '상호금융자금부' 소속입니다" 라고 말했다.
    

#### 5) 컨테이너형

* 여러 자료형을 갖는 다수의 자료들을 하나의 변수에 담는 자료형의 범주
* **리스트(list)** : []로 둘러싸인 데이터들의 집합. 원소간 **순서가 있고**, 원소의 내용을 **변경 가능**
* **튜플(tuple)** : ()로 둘러싸인 데이터들의 집합. 원소 간 **순서가 있고**, 원소의 내용을 **변경 불가**
* **집합(set)** : {}로 둘러싸인 데이터들의 집합. **순서가 없고**, 원소의 내용 **변경 가능**하지만, **중복 불가능**하고, 
* **딕셔너리(dict)** : {키1 : 값1, 키2 : 값2, ...} 형태를 갖고, 원소간 **순서가 없고**, 키워드로 호출할 수 있음


```python
m = [1, 1.5, '개', True]   # 리스트 생성
n = ('사람', m, None)   # 튜플 생성

print(m)
print(n)
print(m[1])
```

    [1, 1.5, '개', True]
    ('사람', [1, 1.5, '개', True], None)
    1.5
    


```python
m[1] = 3.5                 # 리스트의 값은 변경 가능
print(m)

n[0]='동물'
```

    [1, 3.5, '개', True]
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-15-e4907e7eada7> in <module>()
          2 print(m)
          3 
    ----> 4 n[0]='동물'
    

    TypeError: 'tuple' object does not support item assignment



```python
o = {'사람', 3, '3', 3, '사람'}
print(o)

print(o[1])
```

    {3, '3', '사람'}
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-16-9dd75df37b66> in <module>()
          2 print(o)
          3 
    ----> 4 print(o[1])
    

    TypeError: 'set' object does not support indexing



```python
p = {'종류' : '주식', '수량' : 3}

print(p)
print(p['수량'])
```

    {'종류': '주식', '수량': 3}
    3
    

#### 6) 시퀀스형

* 순서가 있는 데이터들의 집합 형태를 갖는 자료형 범주. 문자열(str), 리스트(list), 튜플(tuple)이 시퀀스형 범주에 속한다
* a[0] 과 같은 형태로 원소 추출이 가능함(indexing)
