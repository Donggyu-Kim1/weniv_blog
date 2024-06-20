# 2일차 정리

## 오늘의 상식
- 중국 생성형 AI의 성장 <영상링크>
- 기후위기, 코코아 가격의 상승
- 프론트엔드의 혁신, [Framer](https://www.framer.com/?via=anh72&gad_source=1&gclid=CjwKCAjwg8qzBhAoEiwAWagLrFkl0iN7eGAh70QLjkUpgIoF_sQyK0S4Xh8Oi1fqKzRgTMgJo3bnmBoCFKgQAvD_BwE)
- 'AI & 빅데이터쇼' 개막

## 문자열(str) 자료형
```
# lower() / upper()
# 1. (영어) 단어가 대소문자가 너무 섞여서 전처리가 힘들 때

a = "Hello World"
print(a.lower())    # 출력 값: hello world
print(a.upper())    # 출력 값: HELLO WORLD
```

```
'''
find() / index()
find()와 index()는 특정 데이터를 찾아서 출력해주는 메서드 
다만 두개의 메서드가 완전히 동일한 기능을 수행하는 것은 아님.
찾을 수 없는 문자열일 경우 find는 -1을 반환하는 반면, index는 error를 반환
'''

a = "Hello World"
print(a.find("o"))  # 출력 값: 4
print(a.index("o")) # 출력 값: 4
print(a.find("x"))  # 출력 값: -1, 찾을 수 없기 때문
```

```
# count()

s = "Hello World"
print(s.count("l")) # 출력 값: 3
```

```
# strip, 양쪽의 공백 제거
# 공백도 하나의 문자열에 해당

s = "   Hello World  "
print(s.strip())    # 출력 값: Hello World
```

```
#양쪽의 공백과 ',!'을 제거해주는 method

a = '    ,!!  hello world   '
print(a.strip(' ,!'))   # 출력 값: hello world
```

```
# replace, 문자열 대체

a = "Hello World"
print(a.replace("World", "Universe"))   # 출력 값: Hello Universe

# 텍스트가 다를 경우, 실행은 되지만 바뀌지 않음
```

```
a = "Hello World"
print(a.replace("l", "L"))  # 출력 값: HeLLo WorLd

# 해당되는 문자 전부 바뀜
```

```
# split(), join()
'''
split과 join은 문자열을 나누고 합치는 메서드
이러한 메서드를 통해 원하는 형식으로 데이터를 분할하고 합칠 수 있음
예를 들어 전화번호가 010 1000 1000으로 입력이 되었다면
띄어쓰기로 쪼개 010, 1000, 1000로 만들 수 있으며,
이것을 대쉬(-)로 합쳐 010-1000-1000처럼 만들 수 있음
'''
# 리스트형으로 변환 -> 바로 가져다가 쓸 수 있음

a = "010 1000 1000"
print(a.split())  # 아무것도 안쓰면 공백을 기준으로
                  # 출력 값: ['010', '1000', '1000']
s = "010-1000-1000"
print(s.split("-"))  # 기준: -
                     # 출력 값: ['010', '1000', '1000']

# join
print("-".join(a.split()))  # 나누고 '-'으로 조인
                            # 출력 값: 010-1000-1000
```

```
# rjust() / ljust() / center()
# 지정한 길이를 맞추고 나머지는 지정한 문자로 채워주는 문자

a = "Hello"
print(a.rjust(10,'@'))  # 출력 값: @@@@@Hello
print(a.ljust(10,'@'))  # 출력 값: Hello@@@@@
print(a.center(11,'@')) # 출력 값: @@@Hello@@@

# 고객식별자 -> 고객번호 -> 문자형 '000001' -> 숫자형 1으로 나오는 상황 발생
# 위 함수를 통해 다시 변환

a = 1
print(str(a).rjust(6,'0'))  # 출력 값: 000001
```

```
# zfill
# 주어진 길이만큼 0을 채워서 반환
# 날짜, 데이터 라벨링 등에 사용

a = 1
print(str(a).zfill(6))  # 음수, 문자열도 가능
                        # 출력 값: 000001
filename = '1'.zfill(3) + '.jpg'
print(filename) # 출력 값: 001.jpg
```

```
year = '24'
month = '6'
day = '1'

today = year + month.zfill(2) + day.zfill(2)

print(today)    # 출력 값: 240601
```

```
# 이스케이프 문자

# \n: 새로운 줄을 나타냄
# \t: 탭을 나타냄
# \r: 커서를 오른쪽(줄의 처음)으로 이동
# \": 큰따옴표를 나타냄
# \': 작은따옴표를 나타냄
# \\: 백슬래시를 나타냄

print("Hello\nWorld")   # 출력 값: Hello
                                   world
print("Hello\tWorld")   # 출력 값: Hello    world
print("Hello\rWorld")   # 출력 값: world
print("Hello\"World")   # 출력 값: Hello"World
print("Hello\'World")   # 출력 값: Hello'World
print("Hello\\World")   # 출력 값: Hello\World
```

### 실습 문제
**사용자 정보 입력받기**
    - 사용자의 이름, 나이, 그리고 좋아하는 색깔을 차례로 입력받아서, 입력받은 정보를 출력하는 간단한 프로그램을 만들어보세요.
    - 이 프로그램은 `input()` 함수를 사용하여 사용자의 이름, 나이, 좋아하는 색깔을 입력받습니다.
    - 입력받은 각 정보는 변수에 저장된 후 `print()` 함수로 출력됩니다.
    - 추가적으로 입력된 나이를 숫자로 변환하여 연산에 사용할 수 있습니다 (예: 나이를 더하거나 빼기 등).

```
name = input("이름을 입력하세요: ")
age = int(input("나이를 입력하세요: "))
color = input("좋아하는 색깔을 입력하세요: ")

print(f"이름: {name}, 나이: {age}, 좋아하는 색깔: {color}")
```

**사용자 정보 입력받기2**
- 사용자로부터 좋아하는 음식, 영화, 취미 세 가지를 입력받아 요약해 출력하는 프로그램을 만들어보세요.
- 좋아하는 음식, 영화, 취미에 대한 정보를 입력받아 이를 요약하여 출력합니다.
- `input()` 함수로 각 정보를 받고, 입력받은 정보를 바탕으로 요약 문장을 출력합니다.

```
food = input("좋아하는 음식을 입력하세요: ")
movie = input("좋아하는 영화를 입력하세요: ")
hobby = input("좋아하는 취미를 입력하세요: ")

print(f"oo씨의 좋아하는 음식은 {food}, 좋아하는 영화는 {movie}, 좋아하는 취미는 {hobby}입니다.")
```

**전화번호를 입력받아 지역번호만 추출하는 프로그램**
- `input()` 함수로 전화번호를 입력받습니다.
- `split()` 메서드를 사용하여 '-'를 구분자로 하여 문자열을 나눕니다.
- 리스트 인덱싱을 통해 첫 번째 요소(지역번호)를 추출합니다.
- 입력받은 전화번호 형식이 올바른지 검사하는 간단한 검증 로직을 추가할 수 있습니다.

```
tel = input("전화번호를 입력하세요(- 사용할 것): ")
tel1 = tel.split("-")
print(f"지역 번호: {tel1[0]}")
```

**사용자로부터 문장을 입력받아 특정 단어를 다른 단어로 치환**
- 사용자로부터 문장과 치환하고 싶은 단어, 그리고 새로운 단어를 입력받습니다.
- `replace()` 메서드를 사용하여 문장 내의 특정 단어를 새로운 단어로 치환합니다.
- `replace()` 함수는 원본 문자열을 변경하지 않고 새로운 문자열을 반환함을 유의하세요.
- 대소문자 구분 없이 치환하려면 입력받은 문장과 치환 대상 단어를 모두 소문자 또는 대문자로 변환한 후 처리할 수 있습니다.

```
sentence = input("문장을 입력하세요: ")
word = input("치환하고 싶은 단어를 입력하세요: ")
new_word = input("새로운 단어를 입력하세요: ")

# 소문자로만
print(f"치환된 문자는 다음과 같습니다. \"{sentence.replace(word, new_word).lower()}\"")

# 대문자로만
print(f"치환된 문자는 다음과 같습니다. \"{sentence.replace(word, new_word).upper()}\"")
```

## 논리(bool) 자료형
- True or False
- 덧셈, 곱셈 연산 가능 

```
print(1 == 1)   #
print(1 == 2)   #
print(True == 1) #   
print(False == 0) #  
print(True + 1) #
print(False + 1)    
print(True * 5) 
print(False * 5)    
```