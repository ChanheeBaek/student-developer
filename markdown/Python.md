# Python

### Python이란?

- 쉽고 간결하며 명확함을 지향하는 실용적인 언어
- 동적 형 변환을 지원
  - 변수에 다양한 객체를 자유롭게 할당
- 객체 지향 인터프리터 언어
  - 모든 데이터는 객체
- 범용 프로그래밍 언어

### Python 실행하는 법

1. 대화식 인터프리터를 이용하기
2.  파이썬 프로그램을 파일로 저장하여 실행
   - 주로 .py 확장자를 사용
   - python [파일 이름]을 사용
   - ex) python test.py

###  기본  자료형

```python
int 1, 95, -100						val1 = 1
float -12.0, 234.5					val2 = 1.0
bool True / False # 대소문자 주의		val3 = '1'	#할당되는 순간, 데이터 타입 결정
None None						    print (type(val1))
								   print (type(val2))
    							   print (type(val3))
```



### 순서형  자료형(Sequence)

- 양의 정수로 색인(index)되게 순서대로 객체들이 나열된 모음
- 반복 가능한(iterable)객체
- 순서열 자료형에 적용되는 공통 연산이나 함수 존재

```python
a = "abcd" #문자열
b = ['a', 'b', 'c', 'd'] #리스트
c = ('a', 'b', 'c', 'd') #튜플
```

- 인덱스는 정수(음수 포함) 가능
- 양수는 범위를 벗어 나면 에러를 반환
- 음수는 뒤에서부터 가져옴 

### 순서열 - 문자열

- 변경 불가능한 순서열 객체
- 문자형 객체의 연속된 묶음
- 작은 따옴표, 큰 따옴표 상관없이 시작과 끝만 맞추기
- 여러 줄은 따옴표 세 개를 이용함


- ```python
  str1 = "test"
  str2 = 'test2	'
  str3 = """test
  code3"""
  print("Welcome to Chanhee's page")
  ```

  ```python
  #자주쓰는 문자열 메소드
  replace() # 대체 a.replace("t", "a")
  strip() # 공백제거 a.lstrip() a.rstrip("., ")
  join() # 문자열 합치기 a.join(["abc", "bcd", "cdc"])  a는 구분자
  split() # 문자열 쪼개기 a.split() a.split(',')  구분자 기준으로 쪼개기
  ```

### 문자열 formatting

문자열을 동적으로 만드는 방법

```python
[C기반]
a = "%s:%d" % ('ad', 17)
[Python 기반]
b = "{}:{}".format('ad', 17)
[명시적으로]
c = "{name}:{age}".format(name = 'ad', age = 17)
[Python 3.6이후부터]
name = 'ad'
age = 17
d = f"{name}:{age}"
```

### Sequence 슬라이싱

한 Sequence에서 Sequence의 일부를 추출 가능

- **[start :end :step]**을 명시하여 슬라이스를 정의

- start 오프셋을 명시하지 않으면 0,

- end 오프셋을 명시하지 않으면 마지막 인덱스

- step은 어떻게 이동할 것인지르 명시

- ```python
  a = "Python"
  a[:3] # Pyt
  a[3:] # hon
  a[0:6:2] # Pto
  a[:3:-1] # no
  ```

### 리스트와 튜플

| 리스트                               | 튜플                     |
| :----------------------------------- | ------------------------ |
| - 순서를 갖는 다양한 객체들의 시퀀스 | - 상수 리스트            |
| - 변경 가능한 객체                   | - 변경 불가능한 객체     |
| - [] 또는 list()로 생성              | - () 또는 tuple()로 생성 |

### Sequence의 Packing / Unpacking

#### 패킹 (packing)

​	여러 항목을 리스트나 튜플에 넣는 것

#### 언패킹 (unpacking)

​	리스트나 튜플에 있는 항목을 변수들로 풀어헤쳐 담는 것

```Python
info = 'James', 'male', 27	#tuple 
name, gender, age = info
name, gender, age = 'James', 'male', 27
```

