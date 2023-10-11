---
layout: single
title:  "파이썬 배우기 11 - while문
categories: 파이썬(Python)
tags: [python, 파이썬, 튜토리얼]
toc: true
sidebar:
    nav: "counts"
---


## 03-2 while문

1.   시작 조건을 명시
2.   반복방식 명시
3.   반복시 실행결과 명시
4.   반복이 끝나는 조건 명시
5.   반복이 끝날때 결과 명시


#### 1. while 문의 기본 구조
```
while 조건문:
    수행할_문장1
    수행할_문장2
    수행할_문장3
    ...
```


```python
treeHit = 0
while treeHit < 10 :
    treeHit = treeHit + 1
    print ('나무에 도끼질을 %d번 했습니다.' % treeHit)
    if treeHit == 10 :
        print ('나무가 넘어갑니다.')

```

#### 2. while 문 만들기


```python
prompt = """
    1. Add
    2. Del
    3. List
    4. Quit

    Enter number: """
number = 0
while number != 4 :
    print(prompt)
    number = int(input())

```

#### 3. while 문 강제로 빠져나가기

- 커피값 300원이면 커피를 주고, 많으면 커피와 거스름돈을 주고 다 팔면 중지하는 코드

1.   먼저 True 를 선언하고,
2.   True 조건을 넣어주고,
3.   그렇지 않은 경우를 코드로 넣는다.




```python
coffee = 2
money = 300
while True :
    money = int(input('돈을 넣어주세요'))
    if money == 300 :
        print('커피를 줍니다.')
        coffee = coffee - 1
    elif money > 300 :
        print('거스픔돈 %d를 주고 커피를 줍니다.' % (money - 300))
        coffee = coffee - 1
    elif money < 300 :
        print('돈은 그냥 돌려주고 커피는 주지 않습니다.')
        print('남은 커피의 양은 %d개입니다.' % coffee)
    if coffee == 0 :
        print('커피가 다 떨어졌습니다. 판매를 중지합니다.')
        break
```

    돈을 넣어주세요200
    돈은 그냥 돌려주고 커피는 주지 않습니다.
    남은 커피의 양은 2개입니다.
    돈을 넣어주세요300
    커피를 줍니다.
    돈을 넣어주세요300
    커피를 줍니다.
    커피가 다 떨어졌습니다. 판매를 중지합니다.
    


```python
while True :
    name = str(input('이름: '))
    number = int(input('주민앞번호: '))
    if name == '홍길동' and number == 100101 :
        print('%s님 수료하셨습니다!' % name)
        break
    else :
        print('이름을 다시 입력하세요!')

```


```python
num = 0
while True:
    num = int(input("숫자를 입력하세요: "))
    if num == 0:
        print("종료합니다.")
        break
    else:
        print(num ** 2)
```

#### 4. while 문의 맨 처음으로 돌아가기


```python
a = 0
while a < 10 :
    a = a + 1
    if a % 2 == 0 :
        continue
    print(a, end = " ")
```

    1 3 5 7 9 
