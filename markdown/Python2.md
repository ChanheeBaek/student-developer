### 조건문

```python
if a == b and a > 0:
    pass
elif a != b or b < 0:
    pass
else:
    pass
```

코드 구조를 생성할 때는 **들여쓰기**를 함

pep-8 이라는 Python 코드 권장 스타일에서는 들여쓰기를 4칸 사용

코드 구조에서 아무 일을 하지 않으면, pass를 이용

### 반복문

```python
for [한 요소] in [반복가능한 객체]:
    [실행 내용]
# iterable한 객체 : 객체의 첫 번째 요소부터 마지막 요소까지 순환 가능한 객체
# sequence 또는 iterator 나 generator
while [조건]:
    [실행 내용]

for i in range(1, 50):
    if i < 40:
        continue
    elif i == 51:
        print('찼았다.')
        break
    else:
        print(i)
 else:
    print("못찾았다.")
```

### 컴프리헨션

```python
[표현식 for 항목 in 순회가능한 객체]
list = [x for x in range(10) if x % 2 == 0]
```

### 함수

Python에서 함수는 1급 객체

### 함수의 구성요소

순서 1)인자, 2) 위치인자, 3) 키워드인자

#### 위치인자(Positional arguments)

- 함수의 매개변수를 튜플로 묶기위해 (*)를 사용

- 인자 이름을 지정하지 않고 차례대로 나열

- ```python
  def print_args(*args):
      print('Positional argument:', args)
  print_args(1,2,'as',{'a':1, 'b':2},[1, 2])
  ```

#### 키워드 인자(Keyword arguments)

- 함수의 매개변수를 딕셔너리로 묶기위해 두 개의 (**)를 사용

- 인자 이름을 지정하고 차례대로 나열

- ```python
  def print_kwargs(**kwargs):
  	print("Keyword arguments:", kwargs)
  print_kwargs(animal = 'cat', fruit = 'apple')
  ```

  ​

### 예외처리

```python
try:
    [에러가 날 수 있는 코드]
except Exception:
    [에러 처리 코드]
else:
    [try 성공시 진행]
finally:
    [무조건 실행]
```



### 모듈과 패키지

#### 모듈 - 파이썬 파일 	

#### 패키지 - 파일 디렉토리

- \__init\__.py 파일을 모함하는 디렉토리를 패키지로 간주

```
import [모듈]
import [모듈] as 이름
from [모듈] import [필요한 부분]
```

