# 3일차 정리

## 오늘의 상식

- LLM 성능 압도, 엔트로픽, '클로드 3.5 소네트' 출시
- 영국, ai 각본 영화 상영 취소, 대중들의 반발
- 앱 개발 사이트 [softr](https://www.softr.io/)

## 리스트(list)

- 시퀀스 자료형
- 위치의 특성을 갖고 있어서 정렬할 수 있음
- 가변적인 자료여서 변경 추가 삭제 가능

```
# 리스트 기초
# 다양한 자료형을 리스트에 넣는 것을 권장 X

x = [1, 2, 3]   # csv 파일과 비슷
y = ['apple', 'banana', 'cherry']
z = [1, [2], 3]  # 리스트 안에 리스트 가능

print([2] in z)
print(len(x), len(y))    # 출력 값: 3, 3
# 리스트의 길이가 너무 길 때, 자료 개수
```

```
x = [1, 2, 3]   # csv 파일과 비슷
y = ['apple', 'banana', 'cherry','melon']
# 데이터 매칭에 오류가 생겼을 때 활용 가능

print(len(x) == len(y))    # 출력 값: False
```

```
# 리스트 항목 변경하기
a = [1, 2, 3, 4, 5]
a[0] = 10

print(a)    # 출력 값: 10, 위치를 통해 변경 가능

a = ['apple', 'banana', 'cherry']
a[0] = 'melon'

print(a)    # 출력 값: ['melon', 'banana', 'cherry]
```

```
# 다차원 리스트
a = [[1, 2, 3], [10, 20, 30]]

print(a[0][1])  # 출력 값: 2
print(a[1][2])  # 출력 값: 30
```

```
# 리스트의 연산
a = [1, 2, 3]
b = [4, 5, 6]

print(a + b)    # 출력 값: [1, 2, 3, 4, 5, 6]
print(a * 3)    # 출력 값: [1, 2, 3, 1, 2, 3, 1, 2, 3]
print(b + a)    # 출력 값: [4, 5, 6, 1, 2, 3]
```

```
# 리스트 인덱싱, 슬라이싱
a = [1, 2, 3, 4, 5]

print(a[1:3])    # 출력 값: [2, 3]
print(a[10])     # 출력 값: IndexError: list index out of range
print(a[::-1])     # 출력 값: [5, 4, 3, 2, 1]
```

```
# 자주 쓰는 메서드
a = [1, 2, 3]
a.append(4)
print(a)    # 출력 값: [1, 2, 3, 4]

a.clear()
print(a)    # 출력 값: []

a = [1, 2, 3]
b = a.copy()    # 얕은 복사
print(b)    # 출력 값: [1, 2, 3]

a = [1, 2, 3]
b = a
print(b)    # 출력 값: [1, 2, 3],

b[0] = 10000
print(a)    # 출력 값: [10000, 2, 3]
# copy를 사용하지 않으면 원본도 변경됨

a = [1, 2, 2, 2, 2, 2, 3, 3]
print(a.count(2))    # 출력 값: 5
```

```
# extend(append와 비슷)

a = [1, 2, 3]
a.extend([4, 5, 6]) # 리스트가 풀어져서 구성원이 추가됨
print(a)    # 출력 값: [1, 2, 3, 4, 5, 6]

a.extend('hello')
print(a)    # 출력 값: [1, 2, 3, 4, 5, 6, 'h', 'e', 'l', 'l', 'o']

a = [1, 2, 3]
a.append([4, 5, 6])
print(a)    # 출력 값: [1, 2, 3, [4, 5, 6]]
```

```
# index()
a = [1, 2, 3, 4, 5]
print(a.index(3))    # 출력 값: 2, 위치를 찾아줌
```

```
# insert()
a = [1, 2, 3, 4, 5]
a.insert(1, 10) # insert(자리, 값)

print(a)    # 출력 값: [1, 10, 2, 3, 4, 5]
```

```
# pop()
a = [1, 2, 3, 4, 5]
print(a.pop(2))    # 출력 값: 3 -> 위치의 값을 뺌
print(a)    # 출력 값: [1, 2, 4, 5] -> 3이 빠진 리스트가 됨

l = [1, 2, 3, 4, 5]
while l:
    print(l.pop())  # 출력 값: 5 4 3 2 1 -> 값을 순서대로 뺌

# remove()
a = [1, 2, 3, 4, 5]
a.remove(3)
print(a)    # 출력 값: [1, 2, 4, 5] -> 3이 빠진 리스트가 됨

a = [1, 2, 2, 2, 2, 2, 2, 3, 4, 5]
while a.count(2):
    a.remove(2)
print(a)    # 출력 값: [1, 2, 4, 5]
```

```
# reverse()
# reversed()
a = [1, 2, 3, 4, 5]
a.reverse()
print(a)    # 출력 값: [5, 4, 3, 2, 1]

a = [1, 2, 3, 4, 5]
b = reversed(a)
print(list(b))    # 출력 값: [5, 4, 3, 2, 1]
```

```
# sort()
# sorted()
a = [1, 3, 2, 5, 4]
a.sort()
print(a)    # 출력 값: [1, 2, 3, 4, 5]

a = [5, 4, 3, 2, 1]
b = sorted(a)
print(a)    # 출력 값: [5, 4, 3, 2, 1]
print(b)    # 출력 값: [1, 2, 3, 4, 5]
```

## 튜플(tuple)

- 불변
- 튜플은 변경되면 안되는 정보(예를 들어, 주민번호, 비밀번호 등)에 활용
- Key 값(SQL)
- 튜플은 소괄호 사용
- 연산, 슬라이싱 등 가능(변경만 안됨)

```
# 튜플
a = (1, 2, 3)
print(type(a))    # 출력 값: <class 'tuple'>

b = [1, 2, 3]
c = (1, 2, b)
print(c)    # 출력 값: (1, 2, [1, 2, 3])
```

```
# 단일 튜플
t1 = ()
t2 = (0,) # 단일 값의 튜플을 사용할때 꼭 콤마 사용
t3 = (0)
t4 = (0.1)
print(type(t1)) # 출력 값: tuple
print(type(t2)) # 출력 값: tuple
print(type(t3)) # 출력 값: int
print(type(t4)) # 출력 값: float
```

```
# count()

a = (1, 2, 3, 4, 5)
print(a.count(3))    # 출력 값: 1

# index

a = (1, 2, 3, 4, 5)
print(a.index(3))    # 출력 값: 2
```

## 딕셔너리(dict)

- 사전과 같은 구조
- key(유일)와 value(중복 가능)가 존재
- 시퀀스 자료형 아님

```
# 딕셔너리 예시
Kim = {'age': 25, 
       'name': 'Kim', 
       'gender': 'male', 
       'height': 170, 
       'weight': 60
       }
```

```
# 중복된 key 값 중 마지막 값으로 출력
d = {'one' : '하나', 'one' : '하나2', 'one' : '하나3'}
print(d)  # 출력 값: {'one' : '하나3'}
```
