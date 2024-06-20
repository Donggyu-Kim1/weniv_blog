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
print(a.strip(' ,!'))   # 출력 값: 
```

```
a = '    ,!!  hello world   '
print(a.strip(" ,!"))
```

```
# replace, 문자열 대체

a = "Hello World"
print(a.replace("World", "Universe"))

# 텍스트가 다를 경우, 실행은 되지만 바뀌지 않음
```