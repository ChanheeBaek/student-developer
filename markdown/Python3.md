### 딕셔너리

```
딕셔너리 = {키1: 값1, 키2: 값2}
딕셔너리 = {}
딕셔너리 = dict()

딕셔너리[키]
딕셔너리[키] = 값

len(딕셔너리)
```

### 딕셔너리와 반복문

```python
for 변수 in 딕셔너리: #모든 키 꺼내옴
    반복할 코드
    
for 키, 값 in 딕셔너리.items():
    반복할 코드
    
for 키 in 딕셔너리.keys():
    반복할 코드
    
for 값 in 딕셔너리.values():
    반복할 코드
    
키 in 딕셔너리
키 not in 딕셔너리
```

### 딕셔너리 표현식

```
{키: 값for 키, 값 in 딕셔너리}
{key: value for key, value in dict.fromkeys(['a', 'b']).items()}
{키: 값 for 키, 값 in 딕셔너리 if 조건식}
```

### 세트

```
세트 = {값1, 값2, 값3}
세트 = set(반복가능한 객체)
```

### 세트 표현식

```
{식 for 변수 in 반복가능한값}
{i for i in 'apple'}
```

